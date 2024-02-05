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

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
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
</table>
</div>

---