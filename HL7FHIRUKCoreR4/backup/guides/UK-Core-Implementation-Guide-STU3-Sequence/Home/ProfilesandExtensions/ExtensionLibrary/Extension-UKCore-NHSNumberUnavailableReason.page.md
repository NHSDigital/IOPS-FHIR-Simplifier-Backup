---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberUnavailableReason
---
## StructureDefinition Extension-UKCore-NHSNumberUnavailableReason

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreNHSNumberUnavailableReason'
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
<td>{{pagelink:Profile-Patient,text:Patient}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>NHS Number Unavailable Reason</b>- An example of the extension which states the reason a patient's NHS number is unavailable.<br>
{{pagelink:Example-UKCore-Extension-NHSNumberUnavailableReason}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-NHSNumberUnavailableReason/~issues?level=File">Report Issue for Extension-UKCore-NHSNumberUnavailableReason</a>.
</div>

<h3 id="guidance-nhgsnumberunavailablereason">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-NHSNumberUnavailableReason}}.

---
