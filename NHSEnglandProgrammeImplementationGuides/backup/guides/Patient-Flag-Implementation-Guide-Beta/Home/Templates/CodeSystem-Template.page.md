<!-- The template for a CodeSystem page. Add the following to the top of the page:

---
subject: [CodeSystem url]
issue: [CodeSystem id]
---

{{page:Home/Templates/CodeSystem-Template.page.md}}
-->

<fql>
from
	CodeSystem
where
	url = %subject
select
	Description: description
with header
</fql>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render}}
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
Click here to: {{page:Home/Templates/Feedback-Link.page.md}}</a>
</div>

---