## {{page-title}}

<div class="example">
  <button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table View</button>

  <div id="XML View" class="tabcontent" style="display:block"> 
    <h3>XML</h3>
    {{xml:example-1-careconnect-gpc-immunization-1-response}}
  </div>

  <div id="JSON View" class="tabcontent">
    <h3>JSON</h3>
    {{json:example-1-careconnect-gpc-immunization-1-response}}
  </div>

  <div id="Table View" class="tabcontent">
    <h3>Table</h3>
    {{table:example-1-careconnect-gpc-immunization-1-response}}
  </div>
</div>