---
topic: Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605
---
# StructureDefinition-UKCore-Medication

Defines the UK Core constraints and extensions on the Medication resource for the minimal set of data to query and retrieve medication information.

## Profile Purpose

This profile is primarily used for the identification and definition of a medication for the purposes of prescribing, dispensing, and administering a medication as well as for making statements about medication use. 

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>TimoptolEyeDrops</b> - An example to illustrate a representation of eye drops.  
</br>
{{pagelink:ExampleUKCore-Medication-TimoptolEyeDrops}}
</div>

### Example Usage Scenarios

The UK Core Medication profile will likely not be used in isolation. It does not provide the context for the medication, e.g. the patient or medication related process. It will be typically used as a referenced resource within a `MedicationRequest`, `MedicationDispense`, `MedicationAdministration` or `MedicationStatement`.

---

## Minimum Viable Dataset

A minimum viable dataset that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `code` | A dm+d code for the medication |

### Context For Provider Systems

Providers systems should view elements listed as part of the minimum viable dataset in the same way as FHIR [Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport) elements. Where the data is available, the provider system should include this data within the resource. Additional elements populated may be ignored by consumer systems.

### Context For Consumer Systems

Consumer systems should expect the elements listed as part of the minimum viable dataset to be populated, with business data that should be relevant for the processing of the resource. Additional elements may not be populated by provider systems.

---
