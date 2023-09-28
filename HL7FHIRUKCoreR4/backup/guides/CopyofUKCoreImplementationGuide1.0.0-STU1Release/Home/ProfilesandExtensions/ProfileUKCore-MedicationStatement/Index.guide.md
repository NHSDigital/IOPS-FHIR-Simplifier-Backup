---
topic: Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf
---
# StructureDefinition-UKCore-MedicationStatement

Defines the UK Core constraints and extensions on the MedicationStatement resource for the minimal set of data to query and retrieve medication statement information. 

## Profile Purpose

This profile allows exchange of a record of a medication that is being consumed by a patient. A MedicationStatement may indicate that the individual may be taking the medication now or has taken the medication in the past or will be taking the medication in the future. The source of this information can be the individual, significant other (such as a family member or spouse), or a clinician.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>XML View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Amoxicillin</b> - An example to illustrate a medication statement of Amoxicillin.
</br>
{{pagelink:ExampleUKCore-MedicationStatement-Amoxicillin}}
</div>
<!-- {{pagelink:ExampleUKCore-MedicationStatement-Amoxicillin}} -->

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient current medication
- Record or update a patients current medication.

---

## Minimum Viable Content

A minimum viable content that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `identifer` | To allow the resource to be referenced within/by other resources |
| `basedOn` | To reference to a `MedicationRequest` resource, where applicable |
| `status` | Mandatory element |
| `statusReason` | To expand on the intent of the `status` |
| `medication[x]` | Mandatory element  |
| `subject` | Mandatory element |
| `effective[x]` | To timestamp the statement |
| `dateAsserted` | To timestamp the statement assertion |
| `informationSource` | To identify the source of the information |
| `derivedFrom` | To reference other resources, where applicable |
| `dosageInstruction` | For the dosage instruction for the statement 

### Context For Provider Systems

Providers systems should view elements listed as part of the minimum viable dataset in the same way as FHIR [Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport) elements. Where the data is available, the provider system should include this data within the resource. Additional elements populated may be ignored by consumer systems.

### Context For Consumer Systems

Consumer systems should expect the elements listed as part of the minimum viable dataset to be populated, with business data that should be relevant for the processing of the resource. Additional elements may not be populated by provider systems.

---
