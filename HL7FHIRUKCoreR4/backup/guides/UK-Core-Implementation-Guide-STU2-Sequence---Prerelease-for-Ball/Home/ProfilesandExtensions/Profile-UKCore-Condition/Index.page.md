---
topic: Profile-Condition-78787
---

# StructureDefinition-UKCore-Condition

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreCondition'
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
	name = 'UKCoreCondition'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Bleeding From Ear</b> - An example to illustrate a patient bleeding from ear.<br/>
{{pagelink:Example-UKCore-Condition-BleedingFromEar}}
<br/><br/>
<b>CodingSCT DescId</b> - An example to illustrate the extension which adds a SNOMED CT description Id to CodeableConcept.<br/>
{{pagelink:Example-UKCore-Condition-Extension-CodingSCTDescId}}
<br/><br/>
<b>Condition Episode</b> - An example to illustrate the extension which is used to indicate the episodicity status of a condition.<br/>
{{pagelink:Example-UKCore-Condition-Extension-ConditionEpisode}}
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Condition profile:

- Query for a Patient’s current or historical conditions
- Record or update a Patient’s conditions

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
<td><code>Condition.clinicalStatus</code></td>
<td>The clinical status of the condition.</td>
</tr>
<tr>
<td><code>Condition.verificationStatus</code></td>
<td>The verification status to support the clinical status of the condition.</td>
</tr>
<tr>
<td><code>Condition.severity</code></td>
<td>A subjective assessment of the severity of the condition as evaluated by the clinician.</td>
</tr>
<tr>
<td><code>Condition.code </code></td>
<td>Identification of the condition, problem or diagnosis.</td>
</tr>
<tr>
<td><code>Condition.subject</code></td>
<td>Indicates the patient or group who the condition record is associated with.</td>
</tr>
<tr>
<td><code>Condition.recorder</code></td>
<td>Individual who recorded the record and takes responsibility for its content.</td>
</tr>
</table>

---