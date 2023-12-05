---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationStatementLastIssueDate
---
## StructureDefinition Extension-UKCore-MedicationStatementLastIssueDate

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreMedicationStatementLastIssueDate'
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-MedicationStatement,text:MedicationStatement}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Last Issue Date</b>- An example to illustrate the date when a prescription was last issued.<br>
  {{pagelink:Example-UKCore-Extension-LastIssueDate}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-MedicationStatementLastIssueDate/~issues?level=File">Report Issue for Extension-UKCore-MedicationStatementLastIssueDate</a>.
</div>


---