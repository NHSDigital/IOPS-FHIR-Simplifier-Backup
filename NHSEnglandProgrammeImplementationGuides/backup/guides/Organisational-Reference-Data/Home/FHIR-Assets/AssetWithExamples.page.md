<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  <h3>Tree View</h3>
{{tree}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to: {{page:Home/FHIR-Assets/FeedbackLink.page.md}}
</div>