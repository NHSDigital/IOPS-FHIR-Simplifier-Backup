---
topic: Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae
---
## StructureDefinition-UKCore-AllergyIntolerance

Defines the UK Core constraints and extensions on the AllergyIntolerance resource for the minimal set of data to query and retrieve allergy information.

## Profile Purpose

This profile allows a record of a clinical assessment of an allergy or intolerance; a propensity, or a potential risk to an individual, to have an adverse reaction on future exposure to the specified substance, or class of substance.

Where a propensity is identified, to record information or evidence about a reaction event that is characterised by any harmful or undesirable physiological response that is specific to the individual and triggered by exposure of an individual to the identified substance or class of substance.

Substances include but are not limited to a therapeutic substance administered correctly at an appropriate dosage for the individual; food; material derived from plants or animals; or venom from insect stings.

This resource is used to record physical conditions. It **MUST** not be used to record preferences for or against types of treatment, for example on religious grounds. For such use cases consider the use of the FHIR [Consent](https://www.hl7.org/fhir/consent.html) resource.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Allergy</b> - An example to illustrate an allergy to medication.
</br>
{{pagelink:ExampleUKCore-AllergyIntolerance-050}}<br>
<b>Allergy entered in error</b> - An example to illustrate an allergy which was entered in error and has been marked as ended.
</br>
{{pagelink:ExampleUKCore-AllergyIntolerance-EnteredInError-050}}<br>
<b>Allergy List</b> - An example to illustrate a list of allergies contained in a Bundle resource.
</br>
{{pagelink:ExampleUKCore-Bundle-BundledAllergyList-050}}
</div>

---

## Minimum Viable Dataset

A minimum viable dataset that all provider and consumer systems should support is the following elements.

| Element | Reason | 
| -- | -- |
| `identifer` | To allow the resource to be referenced within/by other resources |
| `clinicalStatus` | To allow consumers to distinguish between `active`, `inactive` and `resolved` records |
| `code` | To identify the causative agent from the SNOMED-CT or dm+d coding systems  |
| `patient` | To identify the patient |
| `recordedDate` | To ensure there is at least one date available to consumer systems to present records chronologically |
| `asserter` | To identify the source of the information |

---


