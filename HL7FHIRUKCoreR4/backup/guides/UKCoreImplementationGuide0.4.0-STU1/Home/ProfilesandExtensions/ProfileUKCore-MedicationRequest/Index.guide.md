---
topic: Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0
---
## StructureDefinition-UKCore-MedicationRequest

Defines the UK Core constraints and extensions on the MedicationRequest resource for the minimal set of data to query and retrieve prescription information.

## Profile Purpose

An order or request for both supply of the medication and the instructions for administration of the medication to an individual. This profile covers inpatient medication orders as well as community orders (whether filled by the prescriber or by a pharmacy). It also includes orders for over-the-counter medications (e.g. Aspirin), total parenteral nutrition and diet/ vitamin supplements. It may be used to support the order of medication-related devices. It is not intended for use in prescribing particular diets, or for ordering non-medication-related items (eyeglasses, supplies, etc).

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Eye drops</b> - An example to illustrate a request for eye drops. 
</br>
{{pagelink:ExampleUKCore-MedicationRequest-EyeDrops}}
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationRequest profile:

- Query for a patient's specific requested medication
- Record or update a requested medication.

---

## Minimum Viable Dataset

A minimum viable dataset that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `identifier` | Allows the resource to be referenced within/by other resources |
| `status` | Mandatory element |
| `intent` | Mandatory element |
| `category` | Provides the business context for the relevant dispensing processes |
| `medication[x]` | Mandatory element |
| `subject` | Mandatory element |
| `authoredOn` | To timestamp the event |
| `requester` | Who is requesting the medication |
| `dosageInstruction` | Dosage instructions for the medication |
| `dispenseRequest` | Specific dispensing quantity instructions |
| `substitution` | Mandatory element |

### Context For Provider Systems

Providers systems should view elements listed as part of the minimum viable dataset in the same way as FHIR [Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport) elements. Where the data is available, the provider system should include this data within the resource. Additional elements populated may be ignored by consumer systems.

### Context For Consumer Systems

Consumer systems should expect the elements listed as part of the minimum viable dataset to be populated, with business data that should be relevant for the processing of the resource. Additional elements may not be populated by provider systems.

---
