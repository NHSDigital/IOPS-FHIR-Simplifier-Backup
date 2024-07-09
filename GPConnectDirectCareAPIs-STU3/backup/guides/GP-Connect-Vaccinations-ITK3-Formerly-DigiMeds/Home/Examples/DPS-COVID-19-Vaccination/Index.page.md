## {{page-title}}

The following FHIR Message would be present as the .DAT file which is sent by the MESH client (or in the body of the HTTP response when downloading a message from the MESH API).

<div class="example">
  <button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="window.open('https://simplifier.net/gpconnect2/vaccination--digimeds--covid-19--data-processing-service/$download?format=xml')">Download</button>
  <button class="nhsd-a-button nhsd-a-button--outline" onclick="window.open('https://simplifier.net/gpconnect2/vaccination--digimeds--covid-19--data-processing-service/$validate')">Validate</button>

  <div id="XML View" class="tabcontent" style="display:block"> 
    <h3>XML</h3>
    {{xml:vaccination--digimeds--covid-19--data-processing-service}}
  </div>

  <div id="Table View" class="tabcontent">
    <h3>Table</h3>
    {{table:vaccination--digimeds--covid-19--data-processing-service}}
  </div>
</div>