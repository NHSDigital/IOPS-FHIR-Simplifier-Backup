---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ResidentialStatus
---
## StructureDefinition Extension-UKCore-ResidentialStatus

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreResidentialStatus'
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
  <b>Residential Status</b>- An example to illustrate the extension to show the patient's residential status.<br>
{{pagelink:Example-UKCore-Extension-ResidentialStatus}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-ResidentialStatus/~issues?level=File">Report Issue for Extension-UKCore-ResidentialStatus</a>.
</div>


<h3 id="guidance-residentialstatus">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-ResidentialStatus}}.

---
