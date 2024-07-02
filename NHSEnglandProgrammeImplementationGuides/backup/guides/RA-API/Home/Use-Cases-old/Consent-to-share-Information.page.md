## {{page-title}}

### Overview

Patient consent must be established for information to be shared through the Reasonable Adjustment Flag or via a 'best interest decision' as per the [Mental Capacity Act (2005)](https://www.nhs.uk/conditions/social-care-and-support-guide/making-decisions-for-someone-else/mental-capacity-act/) – according to existing guidance and best practice. 

Any sharing of patient information must adhere to the [Caldicott Principles](https://www.gov.uk/government/publications/the-caldicott-principles)

In some cases consent can also be obtained from a lasting power of attorney for health and welfare, or a court appointed deputy. Consent is usually obtained by a suitable member of staff discussing the Reasonable Adjustment Flag with the patient, their carer or the appropriate patient representative. The member of staff will then record the type of consent captured, along with some free text details providing more information about who provided the consent.

As an example of best practice, existing guiduance using a 'best interest decision' can be found in the defintion for [consent to treatment](https://www.nhs.uk/conditions/consent-to-treatment). This describe cases where a patient advocate may provide consent when the patient [does not have the capacity to do so](https://www.nhs.uk/conditions/consent-to-treatment/capacity). 

### Use Case

As capacity can sometimes change over time, it should be assessed at the time that consent is required. This will usually be done by an appropriately trained and experienced healthcare professional (i.e. Practitioner) who's either:

* recommending the treatment or investigation
* involved in carrying it out

If the patient does not have the capacity to consent, then a patient advocate may provide consent for them.


<plantuml>
@startuml
skinparam actorStyle awesome

actor Practitioner as pra
package Consenter {
  actor "Patient Advocate" as pad
  actor Patient as pat
}

usecase "Consent to share information" as CON

pat -- CON
pad -- CON
pra -- CON

@enduml
</plantuml>


#### Scenarios

```gherkin
Given a practitioner has received consent from a patient
And the consent is for reasonable adjustments
When a practioner records the consent
Then details of who obtained the consent will be recorded
And the consent will be linked to the patient

Given a patient or their advocate provides consent
And the consent is for reasonable adjustments
When a practioner records the consent
Then consent will be marked as active
And the consent will be linked to the patient

Given a patient or their advocate does not provide consent
And the consent is for reasonable adjustments
When a practioner records the consent
Then consent will be marked as inactive
And the consent will be linked to the patient

Given a patient or their advocate revokes consent
And the consent is for reasonable adjustments
When a practioner records the consent
Then consent will be marked as inactive
And all flags will be deleted
And all conditions will be deleted
```

### Workflow

When consent or dissent is provided by the patient or their advocate, then this will be recorded in a [Consent](https://www.hl7.org/fhir/r4/consent.html) resource.  If there was previous consent to record adjustments, but the consent is then revoked, then all adjustment records must also be removed.

<plantuml>
@startuml

|<font color=gray><b><u>Practioner</u></b></font>|
start
:Request consent;

|#LightGray|<font color=gray><b><u>Patient</u></b></font>|
if (Capacity to\n  consent?) is (Yes) then
:Provide consent; 
else (No)

|<font color=gray><b><u>Patient Advocate</u></b></font>|
:Provide consent; 
endif

|<font color=gray><b><u>Practioner</u></b></font>|
if (Consent given) is (Yes) then
:Record/confirm\n consent given;
else (No)
:    Revoke consent\nand previous records;
endif

|#LightGray|<font color=gray><b><u>API</u></b></font>|
:Update API;
note right
There are vaious
ways this can be
acheived and 
examples are 
provided 
throughout
end note

|<font color=gray><b><u>Practioner</u></b></font>|
:Confirmation;
stop

@enduml
</plantuml>

### System Interactions

If consent is given either by the patient or the patient advocate, then this should be recorded.  A record of who obtained the consent must also be embedded in the Consent resource.  This will done using a contained provenance resource.  

If consent has not been previously given, then this means the Consent resource must be created.  If consent is revoked, then the Consent resource should be updated to reflect this and marked as inactive.  Any previous adjustment records that were recorded must be removed, including the patient flag and all adjustment flags and conditions.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
actor        "Patient Advocate" as pad
participant  "FHIR API"         as api
entity       "Consent"          as con
entity       "Patient Flag"     as pfg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

alt Patient provides consent
  pra ->  pat : Request consent
  pra <-- pat : Provide consent
else Advocate provides consent
  pra ->  pad : Request Consent
  pra <-- pad : Provide consent
end

alt Consent has been given
  pra ->  api : Record consent given
  api ->  con : Create/update resource
  con ->  con : Validate
  api <-- con : return
  alt Validation failed
    api -> api : rollback
  end
  pra <-- api : OperationOutcome
else Consent has not been given/been revoked
  pra ->  api : Record consent was not given
  api ->  con : Create/update resource
  con ->  con : Validate
  api <-- con : return
  alt Validation failed
    api -> api : rollback
  else Consent updated
    api ->  pfg : Delete adjustment patient flag
    api ->  adj : Delete adjustment flag(s)
    api ->  cod : Delete condition flag(s)
  end
  pra <-- api : OperationOutcome
end

@enduml
</plantuml>

### Examples

* [Consent is given example](Consent-RAConsentExample1.html)

**TODO** - *these were not previous modelled in the terminology*

* [Consent is not given](Consent-RAConsentExampleDissent.html)
* [Consent is revoked](Consent-RAConsentExampleRevoked.html)

### Relevant Documentation

* FHIR [ReSTful API](https://www.hl7.org/fhir/R4/http.html)
