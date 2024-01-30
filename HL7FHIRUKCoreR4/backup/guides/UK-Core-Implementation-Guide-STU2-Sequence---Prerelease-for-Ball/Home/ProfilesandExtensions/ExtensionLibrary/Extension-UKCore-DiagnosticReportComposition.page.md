## StructureDefinition Extension-UKCore-DiagnosticReportComposition

<div id="r5Asset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This is a proxy Extension, for pre-adopting of a R5 element.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDiagnosticReportComposition'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-DiagnosticReport-54417,text:DiagnosticReport}}</td>
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
{{tree:http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.composition}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.composition}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.composition}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.composition}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to send a composition resource with a diagnostic report.<br>
  {{pagelink:Example-UKCore-DiagnosticReport-Extension-CompositionReference}}
  <br><br>
</div>

### Guidance
The resource being referenced SHOULD conform to the following {{pagelink:Profile-Composition-31483}}.

---