---
expand: yes
---
## {{page-title}}

GraphDefinition for validating/retrieving a complete Test Result. Only relevant for Structured Reporting where the DiagnosticReport references a series of result/supporting-info/recommended-action/genomic-study resources. The complete result can then be returned via a single API call e.g. to:

```
GET [base]/DiagnosticReport/DiagnosticReport-AnitaLamberts-Example/$graph?graph=genomics-test-result
```

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:https://fhir.nhs.uk/GraphDefinition/genomics-test-result}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/GraphDefinition/genomics-test-result}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/GraphDefinition/genomics-test-result}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/GraphDefinition/genomics-test-result}}
</div>

---