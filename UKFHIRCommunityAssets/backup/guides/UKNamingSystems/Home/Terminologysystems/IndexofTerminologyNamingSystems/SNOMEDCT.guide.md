## `SNOMED CT`

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Overview" class="tabcontent" style="display:block">
  <h3>Overview</h3>
{{render:http://snomed.info/sct, snapshot}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://snomed.info/sct, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://snomed.info/sct, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://snomed.info/sct, snapshot}}
</div>

