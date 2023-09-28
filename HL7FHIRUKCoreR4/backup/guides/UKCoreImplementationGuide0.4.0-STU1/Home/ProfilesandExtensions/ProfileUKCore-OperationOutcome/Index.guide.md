---
topic: Profile-OperationOutcome-07a0844d-75f0-4abe-b99b-7597e8de31f3
---
## StructureDefinition-UKCore-OperationOutcome

Defines the UK Core constraints and extensions on the OperationOutcome resource for the minimal set of data to query and retrieve information about the outcome of an attempted system operation.

## Profile Purpose
The purpose of this profile is to provide detailed information about the outcome of an attempted system operation. Operation outcomes are sets of error, warning and information messages provided as a direct system response, or part of one, and provide information about the outcome of the operation.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
{{pagelink:ExampleUKCore-OperationOutcome-DateError}}


</div>

### Profile Minimum Viable Content


**Each OperationOutcome resource must have:**

- An issue
- An issue.severity
- An issue.code

**Each OperationOutcome resource must support:**

- An issue.details

---

## Profile specific implementation guidance: ##


