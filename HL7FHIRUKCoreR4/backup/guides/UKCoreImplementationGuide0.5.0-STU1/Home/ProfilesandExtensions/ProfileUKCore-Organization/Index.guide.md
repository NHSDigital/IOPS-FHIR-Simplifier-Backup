---
topic: Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8
---
## StructureDefinition-UKCore-Organization

Defines the UK Core constraints and extensions on the Organization resource for the minimal set of data to query and retrieve organisation information.

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
{{pagelink:ExampleUKCore-Organization-Hospital-050}}<br><br>
<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>
{{pagelink:ExampleUKCore-Organization-GPPractice-050}}

</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Organization profile:

- Query for organisation information using the query parameter identifier `Organization.identifier) for a known ODS code.
- Exchange organisation information within a FHIR document or message.

---

## Profile specific implementation guidance: ##

### Minimal Viable Content

As a minimum either a `Organization.identifier` or `Organization.name` should be provided.

All other elements are optional.

---

