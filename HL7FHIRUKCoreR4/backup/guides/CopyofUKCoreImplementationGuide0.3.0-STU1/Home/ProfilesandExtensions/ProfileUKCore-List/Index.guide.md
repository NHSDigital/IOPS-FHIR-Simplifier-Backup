---
topic: Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304
---
## StructureDefinition-UKCore-List

Defines the UK Core constraints and extensions on the List resource for the minimal set of data to query and retrieve a list of information.

## Profile Purpose

This profile allows exchange of a flat, possibly ordered collection of records. The list profile can be used in many places, including allergies, medications, alerts, family history, medical history, etc. This list profile can be used to support individual-specific clinical lists as well as lists that manage workflows such as tracking patients, managing teaching cases, etc. The list profile supports lists that are homogeneous – consisting of only one type of resource (e.g. allergy lists) as well as heterogeneous – containing a variety of resources (e.g. a problem list including Conditions, AllergyIntolerances, recent Procedures, etc.).

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

This example shows the use of an empty List to indicate that there is no content. This is not supposed to represent actual system behavior.

{{pagelink:ExampleUKCore-List-EmptyList-030}}

This example is an example FHIR Bundle that could be returned following a query for the allergies for a patient. Note: the use of List and Bundle is not mandated and is used to illustrate a possible use of the List Profile and is not expected system behaviour.

{{pagelink:ExampleUKCore-Bundle-BundledAllergyList-030}}

</div>

## Example Usage Scenarios ##
The following are example usage scenarios for the UK Core List profile:

- A list of allergies for a Patient
- A list of current medication for a Patient
- Record or update a list of information for Patient

---

## Profile specific implementation guidance: ##


