---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CuffSize
---
## StructureDefinition Extension-UKCore-CuffSize

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Extension added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-CuffSize/~issues?level=File">Report Issue for Extension-UKCore-CuffSize</a>.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCuffSize'
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
<td>{{pagelink:Profile-Device-BloodPressure,text:Device}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Cuff Size</b> - An example to illustrate a blood pressure monitoring device with a large cuff.<br>
{{pagelink:Example-UKCore-Extension-CuffSize}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-CuffSize/~issues?level=File">Report Issue for Extension-UKCore-CuffSize</a>.
</div>

<h3 id="guidance-cuffsize">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-BloodPressure-CuffSize}}.

---
