---
topic: Profile-Composition-31483
---

# StructureDefinition-UKCore-Composition

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreComposition'
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
	name = 'UKCoreComposition'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Discharge</b> - An example to illustrate a composition containing a discharge summary.<br/>
{{pagelink:Example-UKCore-Composition-Discharge}}
<br/><br/>
<b>CareSetting Type</b> - An example to illustrate the care setting of a FHIR document.<br/>
{{pagelink:Example-UKCore-Composition-Extension-CareSettingType}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Composition profile:

- Query for a specific patient document or document type
- Query for recent patient documents
- Create a new document or update an existing document 

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Composition.status</code></td>
<td>The workflow/clinical status of this composition.</td>
</tr>
<tr>
<td><code>Composition.type</code></td>
<td>Specifies the particular kind of composition.</td>
</tr>
<tr>
<td><code>Composition.subject</code></td>
<td>Who and/or what the composition is about.</td>
</tr>
<tr>
<td><code>Composition.author</code></td>
<td>Identifies who is responsible for the information in the composition.</td>
</tr>
<tr>
<td><code>Composition.confidentiality</code></td>
<td>The code specifying the level of confidentiality of the Composition.</td>
</tr>
<tr>
<td><code>Composition.custodian</code></td>
<td>Identifies the organization or group who is responsible for ongoing maintenance of and access to the composition/document information.</td>
</tr>
</table>

---
