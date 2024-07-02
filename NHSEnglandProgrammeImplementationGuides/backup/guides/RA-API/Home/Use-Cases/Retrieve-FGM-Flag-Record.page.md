## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

### Usecase

An FGM Flag Record may be retrieved if it exists.  It will be possible to determine that an flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} with:
- the code `female-genital-mutilation-flag` {{pagelink:England-Flag-Category-Patient}}


<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as res
usecase "Retrieve FGM Flag record" as ret
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

pra ->  api : Query for records
api ->  pfg : Query for records
api <-- pfg : SearchSet Bundle
pra <-- api : SearchSet Bundle

@enduml
</plantuml>

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Patient endpoint search 

This section describes how to query from the [Patient](http://www.hl7.org/fhir/R4/patient.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated flag resources for Female Genital Mutilation records.

```
GET /Patient?identifier=9912003888&_has:Flag:patient:code=FGM
```

This limits the search to patients thant have the identifier `9912003888`

```
identifier=9912003888
```

This limits the search to patients that have Flag resources linked via patient and have the code FGM, and also includes the resource in the returned searchset Bundle.

```
&_has:Flag:patient:code=FGM&_revinclude=Flag:patient
```


The following queries will return all or some of the resources constituing a Female Genital Mutilation record:

* [Patient Flag](StructureDefinition-PatientFlag.html) resources  


This query relies on the [FlagCategory](SearchParameter-FlagCategory.html) and [FlagCode](SearchParameter-FlagCode.html) SearchParameters.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

**NOTE:** For every additional record/resource added, the flag-detail element in the Patient Flag resource will need updated. See **TODO -- link to add interaction diagram**.

If the [flag-detail extension](http://hl7.org/fhir/StructureDefinition/flag-detail) is used, then references to all Reasonable Adjustment resources can be included the [Patient Flag](StructureDefinition-PatientFlag.html) resource.

This will return all associated flag resources for Female Genital Mutilation records.

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


