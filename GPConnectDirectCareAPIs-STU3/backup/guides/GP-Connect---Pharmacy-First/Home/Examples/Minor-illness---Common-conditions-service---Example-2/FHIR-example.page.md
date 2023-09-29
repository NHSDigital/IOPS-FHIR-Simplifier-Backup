## {{page-title}}

The following FHIR Message would be present as the .DAT file which is sent by the MESH client (or in the body of the HTTP response when downloading a message from the MESH API).

<div class="example">
  <button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="window.open('https://simplifier.net/gpconnect2/minor-illness-common-conditions-service--example-2/$download?format=xml')">Download</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="window.open('https://simplifier.net/gpconnect2/minor-illness-common-conditions-service--example-2/$validate')">Validate</button>

  <div id="XML View" class="tabcontent" style="display:block"> 
    <h3>XML</h3>
    {{xml:minor-illness-common-conditions-service--example-2}}
  </div>

  <div id="Table View" class="tabcontent">
    <h3>Table</h3>
    {{table:minor-illness-common-conditions-service--example-1}}
  </div>
</div>