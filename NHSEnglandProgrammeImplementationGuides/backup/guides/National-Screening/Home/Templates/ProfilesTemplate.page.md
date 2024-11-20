<!-- The template for a Profile page. Add the following to the top of the page:

---
topic: [Profile id]
subject: [Profile url]
usage: [baseDefinition (url), e.g. HL7 or UK Core]
issue: [Profile id]
---

{{page:Home/Templates/Profile-Template.page.md}}

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>[Example 1]</b> - [example description 1]<br/>
{{pagelink:[Example page link]}}<br><br>
</div>
</nocheck>


<fql>
from
	StructureDefinition
where
	url = %subject
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description
  with header 
</fql>

<div id="transpose">
</div>
<br>

<fql>
from
	StructureDefinition
where
	url = %subject
select
	Profile_Purpose: purpose
with header 
</fql>
-->

<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'Detailed View')">Detailed View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <!--<button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>-->
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Detailed View" class="tabcontent">
{{dict}}
</div>

<div id="Table View" class="tabcontent">
{{table}}
</div>

<div id="XML View" class="tabcontent">
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
{{json}}
</div>


<div id="Feedback" class="tabcontent">
{{page:Home-Templates-FeedbackTemplatePage}}
</div>