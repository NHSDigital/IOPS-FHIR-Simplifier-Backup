# Bundle

This project will use the UK Core https://www.hl7.org/fhir/bundle.html

The Composition resource is wrapped within the Bundle with a type="document"

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>
<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
  {{tree:http://hl7.org/fhir/StructureDefinition/Bundle, diff}}
</div>
<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
  {{tree:http://hl7.org/fhir/StructureDefinition/Bundle, hybrid}}
</div>
<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
  {{tree:http://hl7.org/fhir/StructureDefinition/Bundle, snapshot}}}
</div>
<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  {{pagelink:ExampleBundleGPInitialSummary}}<br/>
  {{pagelink:ExampleBundleGPSummary}}
</div>