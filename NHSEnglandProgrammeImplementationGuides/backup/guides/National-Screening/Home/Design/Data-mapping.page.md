## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

<plantuml>
@startuml
Group "1" *-- "many" Patient : has
Patient "1" *-- "many" Encounter : has
Patient "1" *-- "many" Observation : has
Patient "1" *-- "many" Flag : has
CarePlan "1" *-- "1" Encounter : has
Patient "1" *-- "many" Appointment : has
Patient "1" *-- "many" Procedure : has
@enduml
</plantuml>

An [xyz] indicator as been modelled around a FHIR R4 Flag.  profile for further guidance. 


<!-- should be a prooper html table not markdown due to styling and accessibility -->
<table class="assets" title="example table">
<tr>
  <th class="width15">Source Data item</th>
  <th class="width10">Cardinality</th>
  <th class="width20">Target FHIR Element</th>
  <th class="width55">Notes</th>
</tr>
<tr>
  <td>Assessment Date</td>
  <td>1..1</td>
  <td>Flag.period.start</td>
  <td>type: <a href='http://hl7.org/fhir/R4/datatypes.html#dateTime'>dateTime</a><br>format: YYYY-MM-DD</td>
</tr>
<tr>
  <td>NHS Number</td>
  <td>1..1</td>
  <td>Flag.identifier:nhsNumber</td>
  <td>type: <a href='http://hl7.org/fhir/R4/search.html#token'>token</a><br>system must be "https://fhir.nhs.uk/Id/nhs-number"<br>value must be a verified NHS number<br>note: a resource reference is not required for FGM-IS.</td> 
</tr>
<tr>
<td>Family history of FGM indicator</td>
<td>1..1</td>
<td>Flag.code.coding</td>
<td>system must be "http://snomed.info/sct"<br>code must be "902961000000107"<br>display must be "Family history of FGM (female genital mutilation)"</td>
</tr>
<tr>
  <td>Status</td>
  <td>1..1</td>
  <td>Flag.status</td>
  <td>See ...</td>
</tr>
<tr>
  <td>Removal Reason</td>
  <td>0..1</td>
  <td>reference </td>
  <td>must be set when Flag.status is not 'active'. E.g. </td>
</tr>
</table>