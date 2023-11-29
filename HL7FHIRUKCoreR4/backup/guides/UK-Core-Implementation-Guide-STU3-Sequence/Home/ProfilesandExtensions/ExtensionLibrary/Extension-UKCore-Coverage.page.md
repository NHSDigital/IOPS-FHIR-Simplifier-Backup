---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage
---
## StructureDefinition Extension-UKCore-Coverage

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCoverage'
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-ServiceRequest,text:ServiceRequest}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Coverage</b>- An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
  {{pagelink:Example-UKCore-Extension-Coverage}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-Coverage/~issues?level=File">Report Issue for Extension-UKCore-Coverage</a>.
</div>

<h3 id="guidance-coverage">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-FundingCategory}}.

---