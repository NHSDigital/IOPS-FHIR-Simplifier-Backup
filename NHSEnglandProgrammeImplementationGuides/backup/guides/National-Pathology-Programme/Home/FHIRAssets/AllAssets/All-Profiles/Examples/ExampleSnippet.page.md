<div class="tab fhirTree">
  <button class="tablinks active" onclick="openTab(event, 'XML')">XML</button>
  <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'Tree')">Tree</button>
  <button class="tablinks" onclick="openTab(event, 'Table')">Table</button>
</div>
    
<div id="XML" role="tabpanel" class="tabcontent"  style="display:block"> 
   {{xml}}
</div>
<div id="JSON" role="tabpanel" class="tabcontent">
   {{json}}
</div>
<div id="Tree" role="tabpanel" class="tabcontent expandedexample">
   {{tree}}
</div>
<div id="Table" role="tabpanel" class="tabcontent">
   {{table}}
</div>