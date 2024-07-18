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


<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to: {{page:Home/Templates/Feedback-Link.page.md}}
</div>