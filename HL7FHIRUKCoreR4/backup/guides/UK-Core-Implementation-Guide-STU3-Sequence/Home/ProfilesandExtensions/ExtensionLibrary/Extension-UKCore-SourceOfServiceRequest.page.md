---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-SourceOfServiceRequest
---
## StructureDefinition Extension-UKCore-SourceOfServiceRequest

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreSourceOfServiceRequest'
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
<td>{{pagelink:Profile-ServiceRequest,text:ServiceRequest}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Source of Service Request</b>- An example to illustrate the source of service request extension associated with a service request.<br>
{{pagelink:Example-UKCore-Extension-SourceOfServiceRequest}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-SourceOfServiceRequest/~issues?level=File">Report Issue for Extension-UKCore-SourceOfServiceRequest</a>.
</div>


<h3 id="guidance-sourceofservicerequest">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-SourceOfServiceRequest}}.

---
