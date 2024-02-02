---
topic: Profile-OperationOutcome
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome
usage: http://hl7.org/fhir/StructureDefinition/OperationOutcome
issue: UKCore-OperationOutcome
---
# StructureDefinition-UKCore-OperationOutcome

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>DateError</b> - An example to illustrate an error returned due to an error in a date.
<br>{{pagelink:Example-UKCore-OperationOutcome-DateError}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios

The following are feasible use cases for the UK Core OperationOutcome profile:

- Query for 
- Exchange of

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
<td><code>OperationOutcome.issue</code></td>
<td>A single issue associated with the action</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.severity</code></td>
<td>Indicates how relevant the issue is to the overall success of the action. This is labelled as "Is Modifier" because applications should not confuse hints and warnings with errors.</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.code</code></td>
<td>Error or warning code</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.expression</code></td>
<td>FHIRPath of element(s) related to issue</td>
</tr>
</table>
</div>

---
