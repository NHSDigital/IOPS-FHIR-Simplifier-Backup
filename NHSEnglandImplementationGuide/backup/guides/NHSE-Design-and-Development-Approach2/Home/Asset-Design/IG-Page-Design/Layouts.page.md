## Extension Layout

Extensions SHALL have a page within the ‘All Extensions’ folder with the naming convention of ‘Extension England-<i>[extensionName]</i>’, and you must ensure the pages within the folder are in alphabetical order.  

Each extension SHALL have an example.  

The page layout SHALL be as the following: 

~~~~html
## StructureDefinition Extension-England-[ExtensionName]

<div id="transpose">
@ ```
from
	StructureDefinition
where
	name = 'ExtensionEnglandAdditionalContact'
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
{ {tree:https://fhir.nhs.uk/StructureDefinition/Extension-England-[ExtensionName]}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.nhs.uk/StructureDefinition/Extension-England-[ExtensionName]}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.nhs.uk/StructureDefinition/Extension-England-[ExtensionName]}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.nhs.uk/StructureDefinition/Extension-England-[ExtensionName]}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>[Example]</b> - An example to illustrate using the extension.<br>
{ {pagelink:Example-England-[Profile]-Extension-[ExtensionName]}}
<br><br>
</div>

### Guidance
[A link to the ValueSet if the Extension has a binding, or a link to the Resource / Profile if the Extension has references]

---
~~~~

---

## ValueSet Layout

ValueSets SHALL have a page within the ‘All ValueSets’ folder with the naming convention “ValueSet <i>[ValueSet id]</i>”, e.g. ValueSet England-EthnicCategory, and you must ensure the pages within the folder are in alphabetical order.  

The layout SHALL be in the following format: 
~~~~html
## England [ValueSet title]

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{ {render:https://fhir.nhs.uk/ValueSet/England-[ValueSet]}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.nhs.uk/ValueSet/England-[ValueSet]}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.nhs.uk/ValueSet/England[ValueSet]}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.nhs.uk/ValueSet/England-[ValueSet]}}
</div>

---
~~~~

The page SHALL be referenced within table on the ‘ValueSets and Codesystems’ page in alphabetical order. 

The page SHALL be referenced within the appropriate profile ‘Bindings (differential)’ table within the profile page. 

---

## CodeSystem Layout

CodeSystems SHALL have a page within the “All CodeSystems” folder with the naming convention “CodeSystem <i>[CodeSystem id]</i>”, e.g. CodeSystem England-EthnicCategory, and you must ensure the pages within the folder are in alphabetical order.  

The layout SHALL be in the following format: 
~~~~html
## England [CodeSystem title]

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{ {render:https://fhir.nhs.uk/CodeSystem/England-[CodeSystem]}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.nhs.uk/CodeSystem/England-[CodeSystem]}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.nhs.uk/CodeSystem/England-[CodeSystem]}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.nhs.uk/CodeSystem/England-[CodeSystem]}}
</div>

---
~~~~

The page SHALL be referenced within table on the ‘ValueSets and Codesystems’ page under the appropriate ValueSet. 

---


## Example Layout

Each example SHALL have its own page within the folder ‘Examples Index’, listed in alphabetical order. The page SHALL be named ‘Example England-<i>[example name]</i>’. 

Each example SHALL also be added to the example tab within the relevant profile and extension table. 

The page layout SHALL be as the following:

~~~~html
### An example to illustrate the [reason for example]

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
 <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{ {table:[Example id]}}
</div>

<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{ {tree:[Example id]}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:[Example id]}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:[Example id]}}
</div>

---
~~~~


<hr class="thickline">