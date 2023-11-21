---
topic: Profile-MedicationRequest
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest
---
# StructureDefinition-UKCore-MedicationRequest

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationRequest'
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
	name = 'UKCoreMedicationRequest'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'Detailed')">Detailed</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Eye drops</b> - An example to illustrate a request for eye drops. 
</br>{{pagelink:Example-UKCore-MedicationRequest-EyeDrops}}
<br><br>
<b>Repeat Information</b> - An example to illustrate the RepeatInformation extension. 
</br>{{pagelink:Example-UKCore-Extension-RepeatInformation}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest'
```
</span>
</div>

<div id="Detailed" class="tabcontent">
  <h3>Detailed Descriptions</h3>
{{dict}}
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-MedicationRequest/~issues?level=File">Report Issue for UKCore-MedicationRequest</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationRequest profile:

- Query for a patient's specific requested medication
- Record or update a requested medication.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>MedicationRequest.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources</td>
</tr>
<tr>
<td><code>MedicationRequest.status</code></td>
<td>A code specifying the current state of the order.</td>
</tr>
<tr>
<td><code>MedicationRequest.intent</code></td>
<td>Whether the request is a proposal, plan, or an original order.</td>
</tr>
<tr>
<td><code>MedicationRequest.category</code></td>
<td>Provides the business context for the relevant dispensing processes</td>
</tr>
<tr>
<td><code>MedicationRequest.medication[x]</code></td>
<td>Identifies the medication being requested.</td>
</tr>
<tr>
<td><code>MedicationRequest.subject</code></td>
<td>Who medication request is for</td>
</tr>
<tr>
<td><code>MedicationRequest.authoredOn</code></td>
<td>To timestamp the event</td>
</tr>
<tr>
<td><code>MedicationRequest.requester</code></td>
<td>Who is requesting the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction</code></td>
<td>Dosage instructions for the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.text</code></td>
<td>Free text dosage instructions.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.timing</code></td>
<td>When medication should be administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate</code></td>
<td>Dosage instructions for the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate.dose[x]</code></td>
<td>Quantity of medication administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate.rate[x]</code></td>
<td>Rate at which the medication is to be administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction</code></td>
<td>Dosage instructions for the medication.</td>
</tr>
<tr>
<td><code>MedicationRequest.dispenseRequest</code></td>
<td>Specific dispensing quantity instructions.</td>
</tr>
<tr>
<td><code>MedicationRequest.dispenseRequest.quantity</code></td>
<td>Amount of medication to supply per dispense.</td>
</tr>
<tr>
<td><code>MedicationRequest.substitution</code></td>
<td>Any restrictions on medication substitution.</td>
</tr>
</table>

---