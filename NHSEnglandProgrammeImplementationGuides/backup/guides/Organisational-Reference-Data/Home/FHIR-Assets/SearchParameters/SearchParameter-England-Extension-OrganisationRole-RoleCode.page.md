---
subject: https://fhir.nhs.uk/England/SearchParameter/England-Extension-OrganisationRole-RoleCode
---
# {{page-title}}

Usage:
- This SearchParameter allows the searching for Organization instance, where the Extension-England-OrganisationRole is present and where the <code>active</code> element is true
- This returns the <code>roleCode</code> element
- The fhirPath expression is: <code>Organization.extension('https://fhir.nhs.uk/England/StructureDefinition/Extension-England-OrganisationRole').extension('roleCode').value</code>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render}}
</div>
<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{{tree}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  None provided at this time.
</div>

<div id="Feedback" class="tabcontent">
<h4><a href='https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Extension-OrganisationRole-RoleCode/~issues?level=File' target="_blank">Propose a change to England-ODS-Role</a></h4>
</div>

---