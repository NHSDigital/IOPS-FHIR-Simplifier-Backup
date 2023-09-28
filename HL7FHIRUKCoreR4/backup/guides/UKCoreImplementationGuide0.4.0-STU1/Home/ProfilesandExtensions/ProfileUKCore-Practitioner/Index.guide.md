---
topic: Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401
---
## StructureDefinition-UKCore-Practitioner

Defines the UK Core constraints and extensions on the Practitioner resource for the minimal set of data to query and retrieve practitioner information.

## Profile Purpose
This profile allows exchange of information about all individuals who are engaged in the healthcare process and healthcare-related services as part of their formal responsibilities and this profile is used for attribution of activities and responsibilities to these individuals.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
</div>


<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>General Practitioner</b> - An example to illustrate a practitioner who is the Patient's GP. 

{{pagelink:ExampleUKCore-Practitioner-PaulRastall}}

<b>Consultant</b> - An example to illustrate a practitioner who is Consultant. 

{{pagelink:ExampleUKCore-Practitioner-SandraGose}}

<b>Pharmacist</b> - An example to illustrate a practitioner who is a Pharmacist.

{{pagelink:ExampleUKCore-Practitioner-JimmyChuck}}

Note: the practitioner's role information is carried in the {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}

</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Practitioner profile:

- Query for practitioner information using the query parameter identifier(practitioner.identifier) for a known SDS identifier
- Exchange practitioner information within a FHIR document or message.


## Profile specific implementation guidance: ##

### Minimal Viable Content

As a minimum either a Practitioner.identifier or Practitioner.name should be provided.

All other elements are optional.



