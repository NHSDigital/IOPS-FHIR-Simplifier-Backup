---
topic: Profile-DocumentReference
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference
---

# StructureDefinition-UKCore-DocumentReference

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDocumentReference'
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
	name = 'UKCoreDocumentReference'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Care Plan Report in PDF</b> - An example to illustrate a...<br/>
{{pagelink:Example-UKCore-DocumentReference-CarePlanReportPDF}}

</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference'
```
</span>
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DocumentReference profile:

- Query for a...
- Record or update a...

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
