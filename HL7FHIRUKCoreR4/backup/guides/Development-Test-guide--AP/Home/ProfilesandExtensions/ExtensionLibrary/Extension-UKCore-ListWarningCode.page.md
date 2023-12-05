---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ListWarningCode
---
## StructureDefinition Extension-UKCore-ListWarningCode


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreListWarningCode'
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
<td>{{pagelink:Profile-List,text:List}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>List Warning Code</b>- An example to illustrate a warning being provided in a List resource.<br>
  {{pagelink:Example-UKCore-Extension-ListWarningCode}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-ListWarningCode/~issues?level=File">Report Issue for Extension-UKCore-ListWarningCode</a>.
</div>

<h3 id="guidance-lsitwarningcode">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-ListWarningCode}}.

---