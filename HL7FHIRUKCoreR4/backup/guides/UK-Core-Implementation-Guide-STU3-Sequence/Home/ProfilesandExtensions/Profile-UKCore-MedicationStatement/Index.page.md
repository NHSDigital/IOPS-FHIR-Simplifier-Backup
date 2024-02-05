---
topic: Profile-MedicationStatement
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement
usage: http://hl7.org/fhir/StructureDefinition/MedicationStatement
issue: UKCore-MedicationStatement
---
# StructureDefinition-UKCore-MedicationStatement

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Amoxicillin</b> - An example to illustrate a medication statement of Amoxicillin.
<br>{{pagelink:Example-UKCore-MedicationStatement-Amoxicillin}}
<br><br>
<b>Last Issue Date</b> - An example to illustrate the LastIssueDate extension.
<br>{{pagelink:Example-UKCore-Extension-LastIssueDate}}
<br><br>
<b>Medication Prescribing Organization Type</b> - An example to illustrate the MedicationPrescribingOrganizationType extension.
<br>{{pagelink:Example-UKCore-Extension-MedicationPrescribingOrganizationType}}
<br><br>
<b>Pharmacist Verified Indicator</b> - An example to illustrate the PharmacistVerifiedIndicator extension. 
<br>{{pagelink:Example-UKCore-Extension-PharmacistVerifiedIndicator}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient's current medication
- Record or update a patient's current medication.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>MedicationStatement.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources.</td>
</tr>
<tr>
<td><code>MedicationStatement.basedOn</code></td>
<td>To reference to a <code>MedicationRequest</code> resource, where applicable.</td>
</tr>
<tr>
<td><code>MedicationStatement.status</code></td>
<td>A code representing the patient or other source's judgement about the state of the medication used that this statement is about.</td>
</tr>
<tr>
<td><code>MedicationStatement.category</code></td>
<td>Indicates where the medication is expected to be consumed or administered.
</td>
</tr>
<tr>
<td><code>MedicationStatement.medication[x]</code></td>
<td>Identifies the medication being administered. </td>
</tr>
<tr>
<td><code>MedicationStatement.subject</code></td>
<td>Who is/was taking the medication.</td>
</tr>
<tr>
<td><code>MedicationStatement.effective[x]</code></td>
<td>To timestamp the statement</td>
</tr>
<tr>
<td><code>MedicationStatement.dateAsserted</code></td>
<td>To timestamp the statement assertion</td>
</tr>
<tr>
<td><code>MedicationStatement.informationSource</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.derivedFrom</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.dosage</code></td>
<td>For the dosage for the statement</td>
</tr>
</table>
</div>

---