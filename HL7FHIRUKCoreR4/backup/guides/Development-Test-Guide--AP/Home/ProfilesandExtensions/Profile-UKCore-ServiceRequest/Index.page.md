---
topic: Profile-ServiceRequest
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest
---
# StructureDefinition-UKCore-ServiceRequest

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreServiceRequest'
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
	name = 'UKCoreServiceRequest'
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
    <b>Additional Contact</b> - An example to illustrate providing an additional contact with a service request.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-AdditionalContact}}
<br><br>
  <b>Colonoscopy Request</b> - An example to illustrate a service request regarding a colonoscopy.<br/>
{{pagelink:Example-UKCore-ServiceRequest-ColonoscopyRequest}}
<br><br>
<b>Coverage</b> - An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-Coverage}}
<br/><br/>
<b>Priority Reason</b> - An example to illustrate the priority reason extension, using a SNOMED CT concept, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-PriorityReason}}
<br><br>
  <b>Priority Reason</b> - An example to illustrate the priority reason extension, using a plain text reason, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-PriorityReason-PlainText}}
<br><br>
<b>Source of Service Request</b> - An example to illustrate the source of service request extension associated with a service request.<br/>
{{pagelink:Example-UKCore-ServiceRequest-Extension-SourceOfServiceRequest}}
<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core ServiceRequest profile:
- Query for service request information for a given Patient
- Exchange service request information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
