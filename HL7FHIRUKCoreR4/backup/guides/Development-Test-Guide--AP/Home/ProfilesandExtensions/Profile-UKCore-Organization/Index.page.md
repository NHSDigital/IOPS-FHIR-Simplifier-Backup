---
topic: Profile-Organization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization
---
# StructureDefinition-UKCore-Organization

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreOrganization'
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
	name = 'UKCoreOrganization'
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
<b>Hospital</b> - Example to illustrate a Hospital organisation.
</br>{{pagelink:Example-UKCore-Organization-LeedsTeachingHospital}}   <br><br>

<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>{{pagelink:Example-UKCore-Organization-WhiteRoseMedicalCentre}}   <br><br>

<b>Extension - mainLocation</b> - Example to illustrate the mainLocation extension.
</br>{{pagelink:Example-UKCore-Organization-Extension-MainLocation}}   <br><br>

<b>Extension - organizationPeriod</b> - Example to illustrate the core-defined organization-period extension.
</br>{{pagelink:Example-UKCore-Organization-Extension-OrganizationPeriod}}
</div>
</nocheck>

### Example Usage Scenarios ###

- Query for organisation information using the query parameter identifier `Organization.identifier` for a known ODS code.
- Exchange organisation information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

