## {{page-title}}

SearchParameter for searching on request references within Specimen, this also allows inclusion of the referenced resources via the _include parameter, e.g. 

`GET [base]/Specimen?_include=Specimen:request`

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:https://fhir.nhs.uk/SearchParameter/request}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/SearchParameter/request}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/SearchParameter/request}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/SearchParameter/request}}
</div>

---