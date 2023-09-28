---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence
---
## StructureDefinition Extension-UKCore-Evidence


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreEvidence'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-AllergyIntolerance,text:AllergyIntolerance}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Evidence</b>- An example to illustrate a reference to results of investigations that confirmed the certainty of the diagnosis for an allergy or intolerance.<br>
{{pagelink:Example-UKCore-Extension-Evidence}}
<br><br>
</div>


<h3 id="guidance-evidence">Extension Specific Guidance</h3>
The resource being referenced SHALL conform to the following {{pagelink:Profile-DiagnosticReport}}.

---