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

An [xyz] indicator as been modelled around a FHIR R4 HealthcareService.

## Organization

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>...</td>
    <td>1..1</td>
    <td>...</td>
    <td>...</td>
  </tr>
</tbody>
</table>

## HealthcareService

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>0..1</td>
    <td>HealthcareService.name</td>
    <td>Description of service as presented to a consumer while searching</td>
  </tr>
  <tr>
    <td>Reference(Location)</td>
    <td>0..*</td>
    <td>HealthcareService.location</td>
    <td>Location(s) where service may be provided</td>
  </tr>
</tbody>
</table>

## Location

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>0..1</td>
    <td>Location.name</td>
    <td>Name of the location as used by humans</td>
  </tr>
</tbody>
</table>

## Schedule

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Actor</td>
    <td>1..*</td>
    <td>Schedule.actor.HealthcareService</td>
    <td>Resource(s) that availability information is being provided for</td>
  </tr>
</tbody>
</table>

## Slot

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Reference(Schedule)</td>
    <td>1..1</td>
    <td>Slot.schedule</td>
    <td>The schedule resource that this slot defines an interval of status information</td>
  </tr>
  <tr>
    <td>Start</td>
    <td>1..1</td>
    <td>Slot.start</td>
    <td>Date/Time that the slot is to begin</td>
  </tr>
  <tr>
    <td>End</td>
    <td>1..1</td>
    <td>Slot.end</td>
    <td>Date/Time that the slot is to conclude</td>
  </tr>
</tbody>
</table>

<!--

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Assessment Date|1..1|Flag.period.start|type: <a href='http://hl7.org/fhir/R4/datatypes.html#dateTime'>dateTime</a><br>format: YYYY-MM-DD
|NHS Number|1..1|Flag.identifier:nhsNumber|type: <a href='http://hl7.org/fhir/R4/search.html#token'>token</a><br>system must be "https://fhir.nhs.uk/Id/nhs-number"<br>value must be a verified NHS number<br>note: a resource reference is not required for FGM-IS. E.g. - {{pagelink:Home/Build/Examples/Example---An-active-FGM-flag.page.md}} 
|Family history of FGM indicator|1..1|Flag.code.coding|system must be "http://snomed.info/sct"<br>code must be "902961000000107"<br>display must be "Family history of FGM (female genital mutilation)"
|Status|1..1|Flag.status|See {{pagelink:Home/FHIRAssets/Profiles/UKCore-Flag.page.md}}
|Removal Reason|0..1|reference {{pagelink:Home/FHIRAssets/Extensions/Index.page.md}}|must be set when Flag.status is not 'active'. E.g. {{pagelink:Home/Build/Examples/Example---A-removed-FGM-flag.page.md}} <br>set on PUT /Flag interaction. E.g. {{pagelink:Home/Design/Interactions.page.md}}

-->