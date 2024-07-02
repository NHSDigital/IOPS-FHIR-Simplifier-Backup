## {{page-title}}
### Overview

For high level requirements, {{pagelink:Home}}.

### Usecase

A Patient Flag Record may be retrieved if it exists.  It will be possible to determine that a adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}   with:

- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}
- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} with a category of `national-reasonable-adjustments-flag` (see {{pagelink:England-Flag-Category-Patient}})
- or the code `national-reasonable-adjustments-flag` (see {{pagelink:England-Flag-Category-Patient}}), 

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as res <<abstract>>
usecase "Retrieve Patient Flag record" as ret <<abstract>>
}

pra -- res
res <.. ret : include

@enduml
</plantuml>

### System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
boundary  "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Additional Detail"  as add

pra ->  api : Query for records
api ->  pfg : Query for records
api <-- pfg : SearchSet Bundle
opt
  loop for each Additional Detail resource type
  api ->  add : Query for records
  api <-- add : SearchSet Bundle
  end
end
pra <-- api : SearchSet Bundle
pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Patient endpoint search 

This section describes how to query from the [Patient](http://www.hl7.org/fhir/R4/patient.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated Flag resources for Patient Flag.

```
GET /PatientFlag?patient=9449306753
```

This limits the search to Flags for the patient that has the identifier `9449306753`

```
patient=9449306753
```


The following queries will return all or some of the resources constituing a Patient Flag record, i.e.

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} resources  
* Any Additional Supporting resources

This query relies on the [FlagCategory](SearchParameter-FlagCategory.html) and [FlagCode](SearchParameter-FlagCode.html) SearchParameters.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

**NOTE:** For every additional record/resource added, the flag-detail element in the Patient Flag resource will need updated. See **TODO -- link to add interaction diagram**.

If the [flag-detail extension](http://hl7.org/fhir/StructureDefinition/flag-detail) is used, then references to all Reasonable Adjustment resources can be included the {{pagelink:  [Patient Flag](StructureDefinition-PatientFlag.html) resource.

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


