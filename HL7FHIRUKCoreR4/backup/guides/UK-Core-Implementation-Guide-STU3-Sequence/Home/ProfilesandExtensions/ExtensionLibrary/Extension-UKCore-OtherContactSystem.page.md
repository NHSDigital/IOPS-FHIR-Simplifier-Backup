---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem
---
## StructureDefinition Extension-UKCore-OtherContactSystem

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreOtherContactSystem'
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
<td>ContactPoint.system</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Other Contact System</b> - An example to illustrate other contact methods for a patient. </br>
{{pagelink:Example-UKCore-Extension-OtherContactSystem}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-OtherContactSystem/~issues?level=File">Report Issue for Extension-UKCore-OtherContactSystem</a>.
</div>

<h3 id="guidance-othercomntactsystem">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-OtherContactSystem}}.

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The datatype of this extension was changed from <code>valueCode</code> in UK Core STU1 Sequence, to <code>valueCodeableConcept</code>, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div> 

---
