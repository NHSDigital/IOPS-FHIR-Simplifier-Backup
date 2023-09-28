## StructureDefinition Extension-UKCore-EthnicCategory

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreEthnicCategory'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Patient-88961,text:Patient}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Ethnic Category</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:Example-UKCore-Patient-Extension-EthnicCategory}}
<br><br>
</div>

### Guidance
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-EthnicCategory}}.

---
