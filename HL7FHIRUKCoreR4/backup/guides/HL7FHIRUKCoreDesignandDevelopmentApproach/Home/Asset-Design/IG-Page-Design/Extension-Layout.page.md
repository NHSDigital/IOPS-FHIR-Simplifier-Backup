## {{page-title}}

Extensions SHALL have a page within the ‘All Extensions’ folder with the naming convention of ‘Extension UKCore-<i>[extensionName]</i>’, and you must ensure the pages within the folder are in alphabetical order.  

Each extension SHALL have an example.  

The page layout SHALL be as the following: 

~~~~html
## StructureDefinition Extension-UKCore-[ExtensionName]

<div id="transpose">
@ ```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAdditionalContact'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{ {pagelink:Profile-[Profile],text:[Profile]}}</td>
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
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[ExtensionName]}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[ExtensionName]}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[ExtensionName]}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[ExtensionName]}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>[Example]</b> - An example to illustrate using the extension.<br>
{ {pagelink:Example-UKCore-[Profile]-Extension-[ExtensionName]}}
<br><br>
</div>

### Guidance
[A link to the ValueSet if the Extension has a binding, or a link to the Resource / Profile if the Extension has references]

---
~~~~

---