<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML</button>
   <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
     
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  {{tree}}
</div>

<div id="JSON View" class="tabcontent">
  {{json}}
</div>

<div id="XML View" class="tabcontent">
  {{xml}}
</div>



<!--
---
<em> Usage note: every effort has been made to ensure that the examples are correct and useful, but they are not a normative part of the specification.</em> --->