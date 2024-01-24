---
topic: Profile-Procedure
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure
usage: http://hl7.org/fhir/StructureDefinition/Procedure
issue: UKCore-Procedure
---
# StructureDefinition-UKCore-Procedure

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Skin Examination</b>- An example to illustrate a procedure of skin examination.<br>
{{pagelink:Example-UKCore-Procedure-ExaminationOfSkin}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Procedure profile:

- Query for procedures performed on a Patient
- Record or update a procedure performed on a Patient

<hr class="thickline">

## Profile specific implementation guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Procedure.status</code></td>
<td>A code specifying the state of the procedure.</td>
</tr>
<tr>
<td><code>Procedure.code</code></td>
<td>A code specifying the state of the procedure.</td>
</tr>
<tr>
<td><code>Procedure.subject</code></td>
<td>Who the procedure was performed on.</td>
</tr>
<tr>
<td><code>Procedure.performed[x]</code></td>
<td>When the procedure was performed.</td>
</tr>
<tr>
<td><code>Procedure.performedDateTime</code></td>
<td>Date and time the procedure was performed.</td>
</tr>
</table>
</div>

---