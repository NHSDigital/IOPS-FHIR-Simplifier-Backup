---
topic: Profile-List
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-List
---
# StructureDefinition-UKCore-List

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreList'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'UKCoreList'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
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

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Empty List</b> - This example shows the use of an empty List to indicate that there is no content. This is not supposed to represent actual system behaviour.
<br>{{pagelink:Example-UKCore-List-EmptyList}}
<br><br>
<b>Bundled Allergy List</b> - This example is an example FHIR Bundle that could be returned following a query for the allergies for a patient. Note: the use of List and Bundle is not mandated and is used to illustrate a possible use of the List Profile and is not expected system behaviour.<br>
{{pagelink:Example-UKCore-Bundle-BundledAllergyList}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-List'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-List'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-List'
```
</span>
</div>
</nocheck>

## Example Usage Scenarios ##
The following are example usage scenarios for the UK Core List profile:

- A list of allergies for a Patient
- A list of current medication for a Patient
- Record or update a list of information for Patient

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
