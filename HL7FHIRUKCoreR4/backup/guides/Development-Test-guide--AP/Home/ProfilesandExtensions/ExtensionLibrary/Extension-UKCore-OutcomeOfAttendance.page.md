---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OutcomeOfAttendance
---
## StructureDefinition Extension-UKCore-OutcomeOfAttendance

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreOutcomeOfAttendance'
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
<td>{{pagelink:Profile-Encounter,text:Encounter}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Outcome of Attendance</b>- An example to illustrate the extension which is used to indicate the outcome of an outpatient attendance.<br>
  {{pagelink:Example-UKCore-Extension-OutcomeOfAttendance}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-OutcomeOfAttendance/~issues?level=File">Report Issue for Extension-UKCore-OutcomeOfAttendance</a>.
</div>


<h3 id="guidance-outcomeofattendanc">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-OutcomeOfAttendance}}.

---