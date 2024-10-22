## {{page-title}}

## {{page-title}}

## {{page-title}}
### Overview

For high level requirements, {{pagelink:Home}}.

### Use Case

A Patient Flag Record may be retrieved if it exists.  It will be possible to determine that adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}   with:

- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} and patient search parameter


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
boundary     "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Additional Detail"  as add

pra ->  api : Query for record
api ->  pfg : Query for record
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
GET [baseUrl]/Flag?patient=9449306753
```

This limits the search to Flags for the patient that has the identifier `9449306753`

```
patient=9449306753
```


The following queries will return all or some of the resources constituting a Patient Flag record, i.e.

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} resources  
* Any Additional Supporting resources

This query relies on the {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}} SearchParameters.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

**NOTE:** For every additional record/resource added, the flag-detail element in the Patient Flag resource will need updated.

If the [flag-detail extension](http://hl7.org/fhir/StructureDefinition/flag-detail) is used, then references to all Additional Detail resources can be included in the {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} resource.

This will return all associated flag resources for the PatientFlag API.

```
http://[baseUrl]/Flag?patient.identifier=9912003888&_include=Flag:detail&_include=Flag:patient
```

This limits the search to patients that have the identifier `9912003888`

```
patient.identifier=9912003888
```

This includes all references in the flag detail extension that have been defined in the {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagDetail.page.md}} SearchParameter.

```
&_include=Flag:detail
```

This query relies on the {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}}, and {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagDetail.page.md}} SearchParameters.

---
