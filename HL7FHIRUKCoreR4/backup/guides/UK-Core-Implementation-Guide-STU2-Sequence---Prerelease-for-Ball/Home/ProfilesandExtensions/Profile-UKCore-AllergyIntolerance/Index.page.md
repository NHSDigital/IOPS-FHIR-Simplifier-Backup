---
topic: Profile-AllergyIntolerance-30748
---
# StructureDefinition-UKCore-AllergyIntolerance

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreAllergyIntolerance'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>

@```
from
	StructureDefinition
where
	name = 'UKCoreAllergyIntolerance'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
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
<br>{{pagelink:Example-UKCore-AllergyIntolerance}}
<br><br>
<b>Allergy entered in error</b> - An example to illustrate an allergy which was entered in error and has been marked as ended.
<br>{{pagelink:Example-UKCore-AllergyIntolerance-EnteredInError}}
<br><br>
<b>Allergy evidence</b> - An example to illustrate a reference to results of investigations that confirmed the certainty of the diagnosis for an allergy or intolerance.
<br>{{pagelink:Example-UKCore-AllergyIntolerance-Extension-Evidence}}
<br><br>
<b>Allergy List</b> - An example to illustrate a list of allergies contained in a Bundle resource.
<br>{{pagelink:Example-UKCore-Bundle-BundledAllergyList}}
</div>
</nocheck>

### Example Usage Scenarios

The following are feasible use cases for the UK Core AllergyIntolerance profile:

- Query for patient allergy information
- Exchange patient allergy information within a FHIR Document or FHIR Message
- Migration of allergies data between systems. 

---

## Profile Specific Implementation Guidance: ##

### Use Case: Query

The query against a clinical system or shared record to return recorded allergies as `AllergyIntolerance` resources.

Returned results could be ordered by `AllergyIntolerance.recordedDate` and/or `AllergyIntolerance.lastOccurrence`.

Returned results MAY include multiple instances of the same allergy, as per the causative agent (`AllergyIntolerance.code`), but with different `AllergyIntolerance.clinicalStatus` values. The newer of such records either by `AllergyIntolerance.recordedDate` or `AllergyIntolerance.lastOccurrence` SHOULD be deemed the latest or current record of the allergy.

### Use Case: Exchange

For when systems need to exchange allergy information within a point-to-point message. The `AllergyIntolerance` resources can be included within a FHIR Message (within the Bundle), or within a FHIR Document alongside other structured resources and text-based data.

Allergy information SHOULD NOT be duplicated between systems (and, in England, this aligns with the NHS Data Strategy). When exchanging allergies data between systems be mindful of whether the receiving system plans to persist the data. If persisted, processes SHALL be put in place to ensure the data is updated if/when the source record is updated.

### Use Case: Migration

When allergy records are migrated between systems, the `AllergyIntolerance` resource could be used as a data migration standard.

Where migrated data is not coded, uses retired / invalidated codes, or coded with a terminology which cannot be mapped to SNOMED CT, then refer to the guidance on using degraded drug / non-drug allergy codes.


---

<div markdown="span" class="alert alert-success" role="alert">
<h3>Minimum Viable Content </h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>AllergyIntolerance.clinicalStatus</code></td>
<td>Defines whether the allergy or intolerance is active, inactive or resolved.</td>
</tr>
<tr>
<td><code>AllergyIntolerance.verificationStatus</code></td>
<td>Defines the assertion of the allergy or intolerance.</td>
</tr>
<tr>
<td><code>AllergyIntolerance.code</code></td>
<td>This code identifies the allergy or intolerance</td>
</tr>
<tr>
<td><code>AllergyIntolerance.patient</code></td>
<td>Links the allergy to the patient</td>
</tr>
<tr>
<td><code>AllergyIntolerance.reaction</code></td>
<td>Details about each adverse reaction event</td>
</tr>
<tr>
<td><code>AllergyIntolerance.reaction.severity</code></td>
<td>Clinical assessment of the severity of the reaction event as a whole</td>
</tr>
</table>
</div>

---

