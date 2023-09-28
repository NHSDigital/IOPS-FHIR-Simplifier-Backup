---
topic: Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8
---
# StructureDefinition-UKCore-Organization

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/organization.html" target="_blank">Organization</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve organisation information.

## Profile Purpose
This profile allows exchange of a formally or informally recognised grouping of people or organisations formed for the purpose of achieving some form of collective action. Includes companies, institutions, corporations, departments, community groups, healthcare practice groups, etc.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Hospital</b> - Example to illustrate a Hospital organisation.
</br>
{{pagelink:ExampleUKCore-Organization-Hospital}}   <br><br>
<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>
{{pagelink:ExampleUKCore-Organization-GPPractice}}   <br><br>
<b>Extension - MainLocation</b> - Example to illustrate the MainLocation extension.
</br>
{{pagelink:ExampleUKCore-Organization-Extension-MainLocation}}   <br><br>

</div>

### Example Usage Scenarios ###


- Query for organisation information using the query parameter identifier `Organization.identifier` for a known ODS code.
- Exchange organisation information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHOULD support are the following elements.

<table id="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>identifier</code>, <code>name</code></td>
<td>As a minimum either <code>Organization.identifier</code> or <code>Organization.name</code> SHOULD be provided.</td>
</tr>
</table>

---