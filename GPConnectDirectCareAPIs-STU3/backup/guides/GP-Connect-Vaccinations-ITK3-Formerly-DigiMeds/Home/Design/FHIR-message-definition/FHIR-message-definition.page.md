## {{page-title}}
<div class="example">
  <button class="nhsd-a-button active" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table View</button>
  <div id="Tree View" class="tabcontent" style="display:block"> 
    <h3>Tree</h3>
    {{tree:https://fhir.nhs.uk/STU3/MessageDefinition/ITK-DM-Immunization-MessageDefinition-1}}
  </div>
  <div id="XML View" class="tabcontent"> 
    <h3>XML</h3>
    {{xml:https://fhir.nhs.uk/STU3/MessageDefinition/ITK-DM-Immunization-MessageDefinition-1}}
  </div>
  <div id="JSON View" class="tabcontent">
    <h3>JSON</h3>
    {{json:https://fhir.nhs.uk/STU3/MessageDefinition/ITK-DM-Immunization-MessageDefinition-1}}
  </div>
  <div id="Table View" class="tabcontent">
    <h3>Table</h3>
    {{table:https://fhir.nhs.uk/STU3/MessageDefinition/ITK-DM-Immunization-MessageDefinition-1}}
  </div>
</div>
