---
topic: Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451
---
## StructureDefinition-UKCore-Procedure

Defines the UK Core constraints and extensions on the Procedure resource for the minimal set of data to query and retrieve the patient’s procedure information.

## Profile Purpose
This profile allows exchange of details of current and historical procedures performed on or for an individual. A procedure is an activity that is performed on, with, or for an individual as part of the provision of care. Examples include surgical procedures, diagnostic procedures, endoscopic procedures, biopsies, counselling, physiotherapy, personal support services, adult day care services, non-emergency transportation, home modification, exercise, etc. Procedures may be performed by a healthcare professional, a service provider, a friend or relative or in some cases by themselves.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

  <b>Skin Examination</b> An example to illustrate a procedure of skin examination
  {{pagelink:ExampleUKCore-Procedure-ExaminationOfSkin}}
  <br>
  An example to illustrate the extension which is used to indicate details of any adverse reaction to any anaesthetic agents including local anaesthesia and problematic intubation, transfusion reaction, etc
{{pagelink:ExampleUKCore-Procedure-Extension-AnaestheticIssues}}


</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Procedure profile:

- Query for procedures performed on a Patient
- Record or update a procedure performed on a Patient

## Profile specific implementation guidance: ##

---

