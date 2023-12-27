---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MainLocation
---
## StructureDefinition Extension-UKCore-MainLocation

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreMainLocation'
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
<td>{{pagelink:Profile-Organization,text:Organization}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Main Location</b>- An example to illustrate the extension of an organisation to carry the main location of that organisation.</br>
{{pagelink:Example-UKCore-Extension-MainLocation}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-MainLocation/~issues?level=File">Report Issue for Extension-UKCore-MainLocation</a>.
</div>


<h3 id="guidance-mainlocation">Extension Specific Guidance</h3>
Where possible, it is expected that the resource being referenced SHOULD conform to {{pagelink:Profile-Location}}.

---
