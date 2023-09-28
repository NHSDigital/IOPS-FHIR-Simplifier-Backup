---
topic: Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9
---
## StructureDefinition-UKCore-MedicationDispense

Defines the UK Core constraints and extensions on the MedicationDispense resource for the minimal set of data to query and retrieve dispensed medication information.

## Profile Purpose
This profile covers the supply of medications to an individual. Examples include dispensing and pick-up from an outpatient or community pharmacy, dispensing patient-specific medications from inpatient pharmacy to ward, as well as issuing a single dose from ward stock to an individual for consumption. The medication dispense is the result of a pharmacy system responding to a medication order.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Eye drops</b> - An example to illustrate a dispense eye drops.  
</br>
{{pagelink:ExampleUKCore-MedicationDispense-EyeDrops}}
</div>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationDispense profile:

- Query for a patient's specific dispensed medication
- Record or update a dispensed medication.

---

## Minimum Viable Content

The minimum viable content that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `identifer` | Allows the resource to be referenced within/by other resources |
| `status` | Mandatory element |
| `statusReason` | To expand on the intent of the `status` |
| `medication[x]` | Mandatory element  |
| `subject` | Identify the patient |
| `performer` | Who or what performed the dispernsing event |
| `authorizingPrescription` | Link to a prescription, when available |
| `quantity` | Quantity of medication dispensed |
| `whenPrepared` | Timestamp the event |
| `dosageInstruction` | Dosage instruction for the dispensed medication |

### Context For Provider Systems

Providers systems should view elements listed as part of the minimum viable dataset in the same way as FHIR [Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport) elements. Where the data is available, the provider system should include this data within the resource. Additional elements populated may be ignored by consumer systems.

### Context For Consumer Systems

Consumer systems should expect the elements listed as part of the minimum viable dataset to be populated, with business data that should be relevant for the processing of the resource. Additional elements may not be populated by provider systems.

---
