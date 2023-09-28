---
topic: Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c
---
## StructureDefinition-UKCore-Patient

Defines the UK Core constraints and extensions on the Patient resource for the minimal set of data to query and retrieve an individual’s demographic information.

## Profile Purpose
This profile allows exchange of demographics and other administrative information about an individual receiving care or other health-related services.

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Richard Smith</b> - An example to illustrate a male patient's demographics. 
</br>
{{pagelink:ExampleUKCore-Patient-RichardSmith-050}}<br>
<b>Melanie Jones</b> - An example of a baby patient. </br>
{{pagelink:ExampleUKCore-Patient-BabyPatient-050}}
<br>
<b>Richard Smith</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:ExampleUKCore-Patient-EthnicCategory-050}}
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter identifier `Patient.identifier` for a known NHS number
- Query for Patient demographic information using query parameters such as `familyName`, `givenName`, `birthDate`, and `gender`.
- Exchange Patient demographic information within a FHIR document or message.

## Profile specific implementation guidance: ##

### Minimal Viable Content

As a minimum either a `patient.identifier` or `patient.name` should be provided.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important:</h4>
When <code>Patient.identifier:nhsNumber</code> is populated  <code>Patient.identifier:nhsNumber.extension:nhsNumberVerificationStatus</code>
must also be populated.
</div>

All other elements are optional.

---
