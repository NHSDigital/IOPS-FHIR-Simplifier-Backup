## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

### FHIR Data Model

<plantuml>
@startuml
HealthcareService "1" *-- "many" Schedule : contains
Schedule "1" *-- "many" Slot : contains
HealthcareService "1" *-- "many" Locations : contains
HealthcareService "1" *-- "1" Organization : contains
Organization "1" *-- "1" OrganizationAffiliation : contains
@enduml
</plantuml>

BELOW TO BE EDITED

An [xyz] indicator as been modelled around a FHIR R4 HealthcareService.


<!-- should be a prooper html table not markdown due to styling and accessibility -->
| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Assessment Date|1..1|Flag.period.start|type: <a href='http://hl7.org/fhir/R4/datatypes.html#dateTime'>dateTime</a><br>format: YYYY-MM-DD
|NHS Number|1..1|Flag.identifier:nhsNumber|type: <a href='http://hl7.org/fhir/R4/search.html#token'>token</a><br>system must be "https://fhir.nhs.uk/Id/nhs-number"<br>value must be a verified NHS number<br>note: a resource reference is not required for FGM-IS. E.g. - {{pagelink:Home/Build/Examples/Example---An-active-FGM-flag.page.md}} 
|Family history of FGM indicator|1..1|Flag.code.coding|system must be "http://snomed.info/sct"<br>code must be "902961000000107"<br>display must be "Family history of FGM (female genital mutilation)"
|Status|1..1|Flag.status|See {{pagelink:Home/FHIRAssets/Profiles/UKCore-Flag.page.md}}
|Removal Reason|0..1|reference {{pagelink:Home/FHIRAssets/Extensions/Index.page.md}}|must be set when Flag.status is not 'active'. E.g. {{pagelink:Home/Build/Examples/Example---A-removed-FGM-flag.page.md}} <br>set on PUT /Flag interaction. E.g. {{pagelink:Home/Design/Interactions.page.md}}