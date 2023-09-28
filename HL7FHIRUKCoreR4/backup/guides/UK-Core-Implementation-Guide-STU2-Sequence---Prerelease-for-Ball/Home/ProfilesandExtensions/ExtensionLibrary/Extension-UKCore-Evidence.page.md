## StructureDefinition Extension-UKCore-Evidence

<!--
A reference to results of investigations that confirmed the certainty of the diagnosis.  Examples might include results of skin prick allergy tests.

### Purpose
This extension extends the AllergyIntolerance resource to support the exchange of information describing the reference to results of investigations that confirmed the certainty of the diagnosis, which is currently not supported by the FHIR standard.

### Guidance
An optional extension for a reference to a `UKCore-DiagnosticReport` resource to share the results of investigations that confirmed the certainty of the allergy or intolerance diagnosis.
-->

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

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-AllergyIntolerance-30748,text:AllergyIntolerance}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Evidence</b>- An example to illustrate a reference to results of investigations that confirmed the certainty of the diagnosis for an allergy or intolerance.<br>
{{pagelink:Example-UKCore-AllergyIntolerance-Extension-Evidence}}
<br><br>
</div>


### Guidance
The resource being referenced SHALL conform to the following {{pagelink:Profile-DiagnosticReport-54417}}.

---