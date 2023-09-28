## {{page-title}}

The structure definition contains the profile’s description and profile purpose, rendered from the xml file using Firely Query Language (FQL). This contains a short description of the profiles purpose and the profile itself within a table. The profile table reference SHALL be rendered as below, ensuring that each view has the correct profile link. 

The tabs and rendered views SHALL be enclosed within a <code>\<nocheck></code> tag to allow for skipping of the spell checker due to the many spelling mistakes within the base HL7 render.

All examples relating to the profile, including those for extensions in the profile, SHALL be included within the Examples view. A profile SHALL have at least one example. 

~~~~html
# StructureDefinition-UKCore-[profile]

<div id="transpose">
@ ```
from
	StructureDefinition
where
	name = 'UKCore[profile name]'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>

@ ```
from
	StructureDefinition
where
	name = 'UKCore[profile name]'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{ {tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-[profile], snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>[profile]</b> - An example to illustrate the [reason for example].
<br>{ {pagelink:Example-UKCore-[profile]}}
</div>
</nocheck>
~~~~

Profile pages built for STU3 Ballot and beyond, SHALL have a `system` within the YAML header, and can replace the snapshot / differential / hybrid tabs, with a single TreeView tab, and utilize the new Simplifier buttons, as these render the page faster. In addition, these should include the new Usage tab.

~~~~html

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
{ {tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{ {table}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>[profile]</b> - An example to illustrate the [reason for example].
<br>{ {pagelink:Example-UKCore-[profile]}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@ ```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = '[resource canonical url]'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@ ```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains '[resource canonical url]'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@ ```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains '[resource canonical url]'
```
</span>
</div>
</nocheck>
---