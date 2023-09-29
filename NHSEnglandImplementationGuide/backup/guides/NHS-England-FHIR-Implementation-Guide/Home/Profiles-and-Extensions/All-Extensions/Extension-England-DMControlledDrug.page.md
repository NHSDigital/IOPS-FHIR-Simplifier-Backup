## StructureDefinition Extension-England-DMControlledDrug

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionEnglandDMControlledDrug'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-England-MedicationRequest, text:MedicationRequest}}
</td>
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
{{tree:https://fhir.nhs.uk/StructureDefinition/Extension-England-DMControlledDrug}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/Extension-England-DMControlledDrug}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/Extension-England-DMControlledDrug}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/Extension-England-DMControlledDrug}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b></b> There is currently no example that uses this extension. An example will be added in a future release. </br>
<br><br>
</div>

<br>

More information about the constraints on the <code>ExtensionEnglandDMControlledDrug</code> can be found below.

<table class="assets" title="Extension England DM Controlled Drug constraint">
<tr>
<th class="width15">Key</th>
<th class="width10">Severity</th>
<th class="width30">Expression</th>
<th class="width45">Human Description</th>
</tr>
<tr>
<td>nhse-con-drug-001</td>
<td>error</td>
<td>(((extension('schedule').value.code='CD2' and extension('quantityWords').exists()) or (extension('schedule').value.code='CD3' and extension('quantityWords').exists()) or (extension('schedule').value.code != 'CD2' and extension('schedule').value.code != 'CD3')) and extension('scheduled').exists()) or (extension('scheduled').exists().not())</td>
<td>Extension(controlledDrug) - For schedule 2 or 3 Controlled Drugs, the quantity must be expressed in words</td>
</tr>
</table>

---
