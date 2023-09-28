---
topic: Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8
---
## StructureDefinition-UKCore-MedicationAdministration

Defines the UK Core constraints and extensions on the MedicationAdministration resource for the minimal set of data to query and retrieve medication administration information.

## Profile Purpose

The purpose of this profile is to describe the event of a patient consuming or otherwise being administered a medication. This may be as simple as swallowing a tablet or it may be a long running infusion. Related resources tie this event to the authorizing prescription, and the specific encounter between patient and health care practitioner. The purpose of this profile is to describe the event of a patient consuming or otherwise being administered a medication. This may be as simple as swallowing a tablet or it may be a long running infusion. Related resources tie this event to the authorizing prescription, and the specific encounter between patient and health care practitioner.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>


<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Timoptol Eye Drops</b> - An example to illustrate a medication administration of eye drops.<br>
 {{pagelink:ExampleUKCore-MedicationAdministration-TimoptolEyeDrops}}  
</div>
</div>


### Example Usage Scenarios

The following are example usage scenarios for the UK Core Medication Administration profile:

- to record and/or share inpatient or outpatient non-immunization administrations. For immunisations use the {{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}} resource.
- to record and/or share patient self-administration of medication. 
- to record and/or share home-health reporting from medicines administration and monitoring devices.

---

## Minimum Viable Content

A minimum viable dataset that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `identifer` | Allow the resource to be referenced within/by other resources |
| `status` | Mandatory element |
| `statusReason` | Expand on the intent of the `status` |
| `medication[x]` | Mandatory element  |
| `subject` | Mandatory element |
| `effective[x]` | Mandatory element |
| `dosage` | The dosage instruction for the administered medication |

### Context For Provider Systems

Providers systems should view elements listed as part of the minimum viable content in the same way as FHIR [Must Support](https://www.hl7.org/fhir/conformance-rules.html#mustSupport) elements. Where the data is available, the provider system should include this data within the resource. Additional elements populated may be ignored by consumer systems.

### Context For Consumer Systems

Consumer systems should expect the elements listed as part of the minimum viable dataset to be populated, with business data that should be relevant for the processing of the resource. Additional elements may not be populated by provider systems.

---
