---
subject: http://hl7.org/fhir/5.0/StructureDefinition/extension-Observation.triggeredBy
---
## StructureDefinition Extension-UKCore-TriggeredBy


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreTriggeredBy'
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
<td>{{pagelink:Profile-Observation,text:Observation}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Triggered By Drug Use</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate a triggering observation.<br>
  {{pagelink:Example-UKCore-Extension-TriggeredBy}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-TriggeredBy/~issues?level=File">Report Issue for Extension-UKCore-TriggeredBy</a>.
</div>

---