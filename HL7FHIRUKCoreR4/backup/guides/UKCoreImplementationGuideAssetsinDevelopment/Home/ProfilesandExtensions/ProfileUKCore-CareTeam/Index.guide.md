---
topic: Profile-CareTeam
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-CareTeam
---

# StructureDefinition-UKCore-CareTeam

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreCareTeam'
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
	name = 'UKCoreCareTeam'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Weight Manangement Team</b> - An example to illustrate a...<br/>
{{pagelink:Example-UKCore-CareTeam-WeightManangementTeam}}

</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-CareTeam'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-CareTeam'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-CareTeam'
```
</span>
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core CareTeam profile:

- Query for a...
- Record or update a...

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
