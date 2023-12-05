---
topic: Profile-Device-BloodPressure
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device-BloodPressure
---

# StructureDefinition-UKCore-Device-BloodPressure

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Device-BloodPressure/~issues?level=File">Report Issue for UKCore-Device-BloodPressure</a>.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDeviceBloodPressure'
select
	Canonical_URL: url,
  Status: status,
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
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Device-BloodPressure/~issues?level=File">Report Issue for UKCore-Device-BloodPressure</a>.
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

