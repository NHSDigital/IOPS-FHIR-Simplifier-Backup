<h3> The profiles are provided for implementation guidance: </h3>

<h3> Note - it is not neccessary to reference the profile in the Resource.meta.</h3>

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
  <h3>Detailed Descriptions</h3>
{{dict}}
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

<!--
<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
{ {page:Home/ProfilesandExtensions/UsageFQLDerived.page.md}}
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
{ {page:Home/ProfilesandExtensions/UsageFQLExtensions.page.md}}
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
{ {page:Home/ProfilesandExtensions/UsageFQLReferences.page.md}}
</span>
</div>
-->

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to: {{page:Home/Templates/Feedback-Link.page.md}}
</div>