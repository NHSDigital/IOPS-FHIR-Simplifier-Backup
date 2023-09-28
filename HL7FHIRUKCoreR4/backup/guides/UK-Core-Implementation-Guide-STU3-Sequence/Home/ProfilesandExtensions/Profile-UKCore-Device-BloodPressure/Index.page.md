---
topic: Profile-Device-BloodPressure
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device-BloodPressure
---

# StructureDefinition-UKCore-Device-BloodPressure

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDeviceBloodPressure'
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
	name = 'UKCoreDeviceBloodPressure'
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
<b>Electronic Sphygmomanometer</b> - An example to illustrate recording of a specific blood pressure device.<br/>
{{pagelink:Example-UKCore-Device-Sphygmomanometer}}<br><br>
<b>Cuff Size</b> - An example to illustrate recording of a cuff size used on a blood pressure device.<br/>
{{pagelink:Example-UKCore-Extension-CuffSize}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device-BloodPressure'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device-BloodPressure'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device-BloodPressure'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Device profile:

- Query and retrieve a information around a blood pressure monitoring / recording device
- Record or update the device used to measure a patient's blood pressure


<hr class="thickline">


## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink: Profile-Device,text:UKCore-Device}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.


<h3>Minimum Viable Content</h3>

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink: Profile-Device,text:UKCore-Device}} table.

---

