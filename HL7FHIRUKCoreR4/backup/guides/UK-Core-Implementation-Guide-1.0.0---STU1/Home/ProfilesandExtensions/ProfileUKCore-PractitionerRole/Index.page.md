---
topic: Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565
---
# StructureDefinition-UKCore-PractitionerRole

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/practitionerrole.html" target="_blank">PractitionerRole</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve practitioner role information.

## Profile Purpose
This profile allows exchange of a specific set of roles, specialties and services that a practitioner may perform at an organisation for a period of time.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Patient's GP</b>- An example to illustrate the role of General Practitioner.
<br>
{{pagelink:Example-UKCore-PractitionerRole-GP}}   <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core PractitionerRole profile:

- Query for a Practitioner role using the query parameter identifier `PractitionerRole.identifier` for a known SDS Role Id.
- Query for a Practitioner using query parameters such as specialty `PractitionerRole.specialty` for a known specialty.
- Exchange Practitioner role information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Minimal Viable Content


<table id="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>identifier, practitioner</code></td>
<td>
As a minimum either a <code>PractitionerRole.identifier</code> or <code>PractitionerRole.practitioner</code> SHOULD be provided.</td>
</tr>
</table>

---