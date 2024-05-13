## {{page-title}}

### Overview

Patient consent must be obtained before retrieving any adjustment or impairment.  See {{pagelink:Home/Use-Cases/Consent-to-share-Information.page.md}} for details of requirements around consent.



### Usecase

After obtaining consent from a patient, a Reasonable Adjustment Record may be retrieved if it exists.  It will be possible to determine that a adjustment flags exist by searching for a [Patient Flag](StructureDefinition-PatientFlag.html) with the code [NRAF](CodeSystem-PatientFlagCategory.html#PatientFlagCategory-NRAF), or [Programme Flags](StructureDefinition-ProgrammeFlag.html) with a category of [NRAF](CodeSystem-PatientFlagCategory.html#PatientFlagCategory-NRAF).

<plantuml>
@startuml

skinparam actorStyle awesome

actor Practitioner as pra
package Consenter {
  actor "Patient Advocate" as pad
  actor Patient as pat
}

usecase "Consent to share information" as CON
usecase "Retrieve Reasonable Adjustment record" as RET

pat -- CON
pad -- CON
pra -- CON
pra -- RET

CON <.. RET : include

@enduml
</plantuml>

### Workflow

A practitioner confirms that a patient consents to share information about Reasonable Adjustment records.  A patient may revoke consent to share information about Reasonable Adjustment records and if they do, all records must be removed.


### System Interaction

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

pra ->  pat : Request confirmation\n       of consent to\n  access information

alt Consent provided
  pra <-- pat : Provide consent

  pra ->  api : Query for records
  pra <-- api : SearchSet Bundle
else Consent not provided
  pra <-- pat : No consent provided
else Consent revoked
  pra <-- pat : Previous consent is revoked

  pra ->  api : Record consent was revoked
  api ->  con : Update resource
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

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Patient endpoint search 

This section describes how to query from the [Patient](http://www.hl7.org/fhir/R4/patient.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated flag resources for Reasonable Adjustments.

```
GET /Patient?identifier=9912003888&_has:Flag:patient:code=NRAF&_has:Flag:patient:category=NRAF&_revinclude=Flag:patient&_has:Consent:patient:category=NRAF&_revinclude=Consent:patient&_has:Condition:patient:category=NRAF&_revinclude=Condition:patient 
```

This limits the search to patients thant have the identifier `9912003888`

```
identifier=9912003888
```

This limits the search to patients that have Flag resources linked via patient and have the code NRAF, and also includes the resource in the returned searchset Bundle.

```
&_has:Flag:patient:code=NRAF&_revinclude=Flag:patient
```

This limits the search to patients that have Flag resources linked via patient and have the category NRAF, and also includes the resource in the returned searchset Bundle.

```
&_has:Flag:patient:category=NRAF&_revinclude=Flag:patient
```

This limits the search to patients that have Consent resources linked via patient and have the category NRAF, and also includes the resource in the returned searchset Bundle.

```
&_has:Consent:patient:category=NRAF&_revinclude=Consent:patient
```

This limits the search to patients that have Condition resources linked via patient and have the category NRAF, and also includes the resource in the returned searchset Bundle.

```
&_has:Condition:patient:category=NRAF&_revinclude=Condition:patient
```

The following queries will return all or some of the resources constituing a Reasonable Adjustments record, i.e.

* [Flag Consent](StructureDefinition-FlagConsent.html) resource
* [Patient Flag](StructureDefinition-PatientFlag.html) resources  
* [Programme Flag](StructureDefinition-ProgrammeFlag.html) resources
* [Flag Condition](StructureDefinition-FlagCondition.html) resources 

This query relies on the [FlagCategory](SearchParameter-FlagCategory.html) and [FlagCode](SearchParameter-FlagCode.html) SearchParameters.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

**NOTE:** For every additional record/resource added, the flag-detail element in the Patient Flag resource will need updated. See **TODO -- link to add interaction diagram**.

<div id="todo-notice" markdown="span" class="alert alert-danger" role="alert">
  <i class="fa fa-tasks"></i>
  <b>TODO: </b>
  <i>Update all interaction diagrams that either add or remove records. Also add new specific diagrams for adding an additional record or removing a single record from a set, where the flag extension then needs updated :(</i>
</div>

If the [flag-detail extension](http://hl7.org/fhir/StructureDefinition/flag-detail) is used, then references to all Reasonable Adjustment resources can be included the [Patient Flag](StructureDefinition-PatientFlag.html) resource.

This will return all associated flag resources for Reasonable Adjustments.

```
http://localhost:8080/fhir/Flag?patient.identifier=9912003888&_include=Flag:detail&_include=Flag:patient
```

This limits the search to patients thant have the identifier `9912003888`

```
patient.identifier=9912003888=9912003888
```

This includes all references in the flag detail extension that have been defined in the [FlagDetail](SearchParameter-FlagDetail.html) SearchParameter.

```
&_include=Flag:detail
```

This includes the associated patient resource.

```
&_include=Flag:patient
```

This query relies on the [FlagCategory](SearchParameter-FlagCategory.html), [FlagCode](SearchParameter-FlagCode.html) and [FlagDetail](SearchParameter-FlagDetail.html) SearchParameters.


### Relevant Documentation

* FHIR [Search](http://www.hl7.org/fhir/R4/search.html)
* [SearchParameters](https://www.hl7.org/fhir/R4/searchparameter.html)