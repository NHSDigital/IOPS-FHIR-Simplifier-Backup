---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact
---
## StructureDefinition Extension-UKCore-AdditionalContact

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAdditionalContact'
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
  <b>Additional Contact</b> - An example to illustrate providing an additional contact with a service request.<br>
{{pagelink:Example-UKCore-Extension-AdditionalContact}}
<br><br>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-AdditionalContact/~issues?level=File">Report Issue for Extension-UKCore-AdditionalContact</a>.
</div>

<h3 id="guidance-additionalcontact">Extension Specific Guidance</h3>

Where possible, it is expected that the resource being referenced SHOULD conform to one of the following UK Core profiles:

- {{pagelink:Profile-Organization}}
- {{pagelink:Profile-Practitioner}}
- {{pagelink:Profile-PractitionerRole}}


---
