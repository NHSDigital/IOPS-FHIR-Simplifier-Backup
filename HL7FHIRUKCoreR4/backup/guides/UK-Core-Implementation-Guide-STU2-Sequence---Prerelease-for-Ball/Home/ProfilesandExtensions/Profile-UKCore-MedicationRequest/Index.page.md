---
topic: Profile-MedicationRequest-20572
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
</br>{{pagelink:Example-UKCore-MedicationRequest-EyeDrops}}
<br><br>
<b>Extension - RepeatInformation</b> - An example to illustrate the RepeatInformation extension. 
</br>{{pagelink:Example-UKCore-MedicationRequest-Extension-RepeatInformation}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationRequest profile:

- Query for a patient's specific requested medication
- Record or update a requested medication.

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