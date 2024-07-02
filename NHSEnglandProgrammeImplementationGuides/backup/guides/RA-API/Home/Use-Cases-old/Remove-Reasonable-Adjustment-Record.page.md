## {{page-title}}

### Overview

A patient may deny or revoke their consent to share adjustment or impairment information at any point. See {{pagelink:Home/Use-Cases/Consent-to-share-Information.page.md}} for details of requirements around consent.
 

#### UseCase

If a patient denys consent, then this must be recorded and all adjustment records must be removed.

<plantuml>
@startuml

skinparam actorStyle awesome

actor Practitioner as pra
package Consenter {
  actor "Patient Advocate" as pad
  actor Patient as pat
}

usecase  "Consent to share information" as CON
usecase "Remove Reasonable Adjustment record" as RET

pat -- CON
pad -- CON
pra -- CON
pra -- RET
CON <.. RET : include


@enduml
</plantuml>


#### Workflow
<p>
  
A patient may revoke consent to share information about Reasonable Adjustment records and if they do, all records must be removed.

</p>

### System Interactions

In the following sequence diagram, a patient revokes consent.  The Consent resource is updated to reflect the patient dissent, and all adjustment records are deleted.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Consent"          as con
entity       "Patient Flag"     as pfg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

  pra ->  pat : Request consent
  pra <-- pat : Deny/revoke consent

  pra ->  api : Record consent was not given
  api ->  con : Update resource
  con ->  con : Validate
  api <-- con : return
  alt Validation failed
    api -> api : rollback
    pra <-- api : OperationOutcome
  else Validation passed
    api ->  pfg : Delete adjustment patient flag
    api ->  adj : Delete adjustment flag(s)
    api ->  cod : Delete condition flag(s)
    pra <-- api : OperationOutcome
  end

@enduml
</plantuml>

The following resource types will be deleted from the record if consent is not granted i.e.

* [Patient Flag](StructureDefinition-PatientFlag.html)  
* [Programme Flag](StructureDefinition-ProgrammeFlag.html)  
* [Condition Flag](StructureDefinition-FlagCondition.html) 

#### Example

Multiple resources can be deleted using a transaction bundle.  This [example delete transaction Bundle](Bundle-RemoveRARecordExample.html) demonstates deleting the following resources

* [Patient Flag](Flag-RAPatientFlagExample1.html) example.  
* [Programme Flag](Flag-RAFlagExample1.html) example.  
* [Condition Flag](Condition-RAConditionExample1.html) example.  

### Relevant Documentation

* [Bundle](https://hl7.org/fhir/r4/bundle.html)  
* [Transaction](https://hl7.org/fhir/r4/http.html#transaction)  