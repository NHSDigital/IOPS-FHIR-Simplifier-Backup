## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

### Usecase

A Reasonable Adjustment Record may be retrieved if it exists.  It will be possible to determine that a adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} with: 
- the code `national-reasonable-adjustments-flag` (see {{pagelink:England-Flag-Category-Patient}}), 
- or {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} with a category of `national-reasonable-adjustments-flag` (see {{pagelink:England-Flag-Category-Patient}}).

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as record
usecase "Retrieve Reasonable Adjustment record" as add
}


package "Patient or Proxy" {
  actor Patient as pat
  actor "Patient Advocate" as pad
}

usecase "Consult" as consult

pat -- consult
pra -- consult
pad -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

### System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

  pra ->  api : Query for records

      api -> pfg : Query for records
      api -> adj : Query for records
      api -> cod : Query for records

  api ->  api : Assemble returns
  pra <-- api : SearchSet Bundle


@enduml
</plantuml>

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Patient endpoint search 

This section describes how to query from the [Patient](http://www.hl7.org/fhir/R4/patient.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated flag resources for Reasonable Adjustments.

```
GET /Patient?identifier=9912003888&_has:Flag:patient:code=NRAF&_has:Flag:patient:category=NRAF&_revinclude=Flag:patient&_has:Condition:patient:category=NRAF&_revinclude=Condition:patient 
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

This limits the search to patients that have Condition resources linked via patient and have the category NRAF, and also includes the resource in the returned searchset Bundle.

```
&_has:Condition:patient:category=NRAF&_revinclude=Condition:patient
```

The following queries will return all or some of the resources constituing a Reasonable Adjustments record, i.e.

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} 

This query relies on the {{pagelink:Home/FHIR-Assets/SearchParameters/England-SearchParameter-FlagCategory.page.md}} and **[FlagCode](SearchParameter-FlagCode.html)-MISSING** SearchParameters.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

**NOTE:** For every additional record/resource added, the flag-detail element in the Patient Flag resource will need updated. See **TODO -- link to add interaction diagram**.

If the [flag-detail extension](http://hl7.org/fhir/StructureDefinition/flag-detail) is used, then references to all Reasonable Adjustment resources can be included the {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} resource.

This will return all associated flag resources for Reasonable Adjustments.

```
http://localhost:8080/fhir/Flag?patient.identifier=9912003888&_include=Flag:detail&_include=Flag:patient
```

This limits the search to patients thant have the identifier `9912003888`

```
patient.identifier=9912003888=9912003888
```

This includes all references in the flag detail extension that have been defined in the {{pagelink:Home/FHIR-Assets/SearchParameters/England-SearchParameter-FlagDetail.page.md}} SearchParameter.

```
&_include=Flag:detail
```

This includes the associated patient resource.

```
&_include=Flag:patient
```

This query relies on the {{pagelink:Home/FHIR-Assets/SearchParameters/England-SearchParameter-FlagCategory.page.md}}, **[FlagCode](SearchParameter-FlagCode.html)-MISSING** and {{pagelink:Home/FHIR-Assets/SearchParameters/England-SearchParameter-FlagDetail.page.md}} SearchParameters.

