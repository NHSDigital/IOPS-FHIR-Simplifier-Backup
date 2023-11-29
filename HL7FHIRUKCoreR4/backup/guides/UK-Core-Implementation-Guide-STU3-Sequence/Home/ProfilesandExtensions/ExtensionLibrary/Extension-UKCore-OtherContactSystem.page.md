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

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  <h3>Tree View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>

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

---
