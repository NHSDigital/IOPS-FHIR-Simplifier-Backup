---
topic: Profile-Condition
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition
usage: http://hl7.org/fhir/StructureDefinition/Condition
issue: UKCore-Condition
---

# StructureDefinition-UKCore-Condition

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Bleeding From Ear</b> - An example to illustrate a patient bleeding from ear.<br/>
{{pagelink:Example-UKCore-Condition-BleedingFromEar}}
<br/><br/>
<b>CodingSCT DescId</b> - An example to illustrate the extension which adds a SNOMED CT description Id to CodeableConcept.<br/>
{{pagelink:Example-UKCore-Extension-CodingSCTDescId}}
<br/><br/>
<b>Condition Episode</b> - An example to illustrate the extension which is used to indicate the episodicity status of a condition.<br/>
{{pagelink:Example-UKCore-Extension-ConditionEpisode}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Condition profile:

- Query for a Patient’s current or historical conditions
- Record or update a Patient’s conditions

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
</div>

---