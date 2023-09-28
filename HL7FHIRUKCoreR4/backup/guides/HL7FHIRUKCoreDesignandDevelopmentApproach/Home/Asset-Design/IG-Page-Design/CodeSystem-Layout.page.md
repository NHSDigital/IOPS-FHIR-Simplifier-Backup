## {{page-title}}

CodeSystems SHALL have a page within the “All CodeSystems” folder with the naming convention “CodeSystem <i>[CodeSystem id]</i>”, e.g. CodeSystem UKCore-EthnicCategoryEngland, and you must ensure the pages within the folder are in alphabetical order.  

The page SHALL be referenced within table on the ‘ValueSets and Codesystems’ page in the ‘Narrative’ index under the appropriate ValueSet, and the ‘Alphabetical (CodeSystems)’ index. 

The layout SHALL be in the following format: 

~~~~html
## UK Core [CodeSystem title]

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{ {render:https://fhir.hl7.org.uk/CodeSystem/UKCore-[CodeSystem]}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.hl7.org.uk/CodeSystem/UKCore-[CodeSystem]}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.hl7.org.uk/CodeSystem/UKCore-[CodeSystem]}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.hl7.org.uk/CodeSystem/UKCore-[CodeSystem]}}
</div>

---
~~~~


---