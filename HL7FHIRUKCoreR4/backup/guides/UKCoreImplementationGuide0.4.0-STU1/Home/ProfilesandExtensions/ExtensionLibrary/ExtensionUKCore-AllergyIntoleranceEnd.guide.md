## StructureDefinition Extension-UKCore-AllergyIntoleranceEnd
Supports the date when the allergy or intolerance was no longer valid, and/or, the reason why the allergy or intolerance is no longer valid.

### Purpose
This extension extends the AllergyIntolerance resource to support the exchange of information describing the date when the allergy or intolerance was no longer valid, and/or, the reason why the allergy or intolerance is no longer valid, which is currently not supported by the FHIR standard.

### Guidance

An optional extension to record the date and reason when the allergy was no longer clinically `active`.<br/>
If the `clinicalStatus` is `active` then this extension **MUST** be omitted.<br/>
If the `clinicalStatus` is `inactive` or `resolved` then the date and reason when the allergy was identified as no longer `active` should be populated.

<table id="assets">
<tr>
<th colspan="2">Context of Use</th>
</tr>
<tr>
<td>Use on element</td>
<td>AllergyIntolerance</td>
</tr>
</table>
<br/>

<div>
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, snapshot}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, snapshot}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  {{pagelink:ExampleUKCore-AllergyIntolerance-AllergyIntoleranceEnd}}
</div>




---