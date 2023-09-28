---
topic: Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae
---
# StructureDefinition-UKCore-AllergyIntolerance

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/allergyintolerance.html" target="_blank">AllergyIntolerance</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve allergy information.
<br>

## Profile Purpose

This profile allows a record of a clinical assessment of an allergy or intolerance; a propensity, or a potential risk to an individual, to have an adverse reaction on future exposure to the specified substance, or class of substance.

Where a propensity is identified, to record information or evidence about a reaction event that is characterised by any harmful or undesirable physiological response that is specific to the individual and triggered by exposure of an individual to the identified substance or class of substance.

Substances include but are not limited to a therapeutic substance administered correctly at an appropriate dosage for the individual; food; material derived from plants or animals; or venom from insect stings.

This resource is used to record physical conditions. It SHALL NOT be used to record preferences for or against types of treatment, for example on religious grounds. For such use cases consider the use of the FHIR <a href="https://hl7.org/fhir/R4/consent.html" target="_blank">Consent</a> resource.

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
{{pagelink:ExampleUKCore-AllergyIntolerance}}
<br><br>
<b>Allergy entered in error</b> - An example to illustrate an allergy which was entered in error and has been marked as ended.
</br>
{{pagelink:ExampleUKCore-AllergyIntolerance-EnteredInError}}
<br><br>
<b>Allergy evidence</b> - An example to illustrate a reference to results of investigations that confirmed the certainty of the diagnosis for an allergy or intolerance.
</br>
{{pagelink:ExampleUKCore-UKCore-AllergyIntolerance-Extension-Evidence}}
<br><br>

</div>

### Example Usage Scenarios

The following are feasible use cases for the UK Core AllergyIntolerance profile:

- Query for patient allergy information
- Exchange patient allergy information within a FHIR Document or FHIR Message
- Migration of allergies data between systems. 

---

## Profile Specific Implementation Guidance: ##

### Use Case: Query

The query against a clinical system or shared record to return recorded allergies as `AllergyIntolerance` resources.

Returned results could be ordered by `recordedDate` and/or `lastOccurrence`.

Returned results MAY include multiple instances of the same allergy, as per the causative agent (`code`), but with different `clinicalStatus` values. The newer of such records either by `recordedDate` or `lastOccurrence` SHOULD be deemed the latest or current record of the allergy.

### Use Case: Exchange

For when systems need to exchange allergy information within a point-to-point message. The `AllergyIntolerance` resources can be included within a FHIR Message (within the Bundle), or within a FHIR Document alongside other structured resources and text-based data.

Allergy information SHOULD NOT be duplicated between systems (and, in England, this aligns with the NHS Data Strategy). When exchanging allergies data between systems be mindful of whether the receiving system plans to persist the data. If persisted, processes SHALL be put in place to ensure the data is updated if/when the source record is updated.

### Use Case: Migration

When allergy records are migrated between systems, the `AllergyIntolerance` resource could be used as a data migration standard.

Where migrated data is not coded, uses retired / invalidated codes, or coded with a terminology which cannot be mapped to SNOMED CT, then refer to the guidance on using degraded drug / non-drug allergy codes.

---


