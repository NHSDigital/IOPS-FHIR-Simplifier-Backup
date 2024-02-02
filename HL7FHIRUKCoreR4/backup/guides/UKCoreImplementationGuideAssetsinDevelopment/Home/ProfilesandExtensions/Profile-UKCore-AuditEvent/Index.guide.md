---
topic: Profile-AuditEvent
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-AuditEvent
usage: http://hl7.org/fhir/StructureDefinition/AuditEvent
issue: UKCore-AuditEvent
---

# StructureDefinition-UKCore-AuditEvent

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Query</b> - An example to illustrate a...<br/>
{{pagelink:Example-UKCore-AuditEvent-Query}}

</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-AuditEvent'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-AuditEvent'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-AuditEvent'
```
</span>
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Audit Event profile:

- Query for a...
- Record or update a...

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
