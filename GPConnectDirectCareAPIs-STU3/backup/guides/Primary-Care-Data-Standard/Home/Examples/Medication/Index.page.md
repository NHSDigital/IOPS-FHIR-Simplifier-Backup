## {{page-title}}

<button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML</button>
<button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'JSON View')">JSON</button>
<button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table</button>

<div class="example" class="nhsd-!t-margin-bottom-6">
  <div id="XML View" class="tabcontent nhsd-!t-margin-bottom-6" style="display:block"> 
    {{xml:example--gpc-data-model--medication}}
  </div>

  <div id="JSON View" class="tabcontent nhsd-!t-margin-bottom-6">
    {{json:example--gpc-data-model--medication}}
  </div>

  <div id="Table View" class="tabcontent nhsd-!t-margin-bottom-6">
    {{table:example--gpc-data-model--medication}}
  </div>
</div>

---