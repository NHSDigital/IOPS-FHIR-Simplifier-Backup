## StructureDefinition Extension-UKCore-CodingSCTDescDisplay

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCodingSCTDescDisplay'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>Coding</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Coding SNOMED CT Description Id</b>- An example to illustrate the extension of adding a SNOMED CT description Id and display Term.<br>
{{pagelink:Example-UKCore-Condition-Extension-CodingSCTDescId}}
<br><br>
</div>

### Guidance

This extension is used alongside the HL7 core-defined [coding-sctdescid](https://hl7.org/fhir/R4/extension-coding-sctdescid.html) to support the exchange of the selected description display term for a SNOMED CT concept, where the selected display term is different to the preferred term. Specific guidance on the usage of this extension can be found within the {{pagelink:Guidance-CodeableConcept}}

---