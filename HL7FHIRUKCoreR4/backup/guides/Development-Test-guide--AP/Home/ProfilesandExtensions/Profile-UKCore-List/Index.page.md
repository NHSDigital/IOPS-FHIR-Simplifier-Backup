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
	name = 'UKCoreList'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Empty List</b> - This example shows the use of an empty List to indicate that there is no content. This is not supposed to represent actual system behaviour.
<br>{{pagelink:Example-UKCore-List-EmptyList}}
<br><br>
<b>Bundled Allergy List</b> - This example is an example FHIR Bundle that could be returned following a query for the allergies for a patient. Note: the use of List and Bundle is not mandated and is used to illustrate a possible use of the List Profile and is not expected system behaviour.<br>
{{pagelink:Example-UKCore-Bundle-AllergyList}}
<br><br>
  <b>List Warning Code</b>- An example to illustrate a warning being provided in a List resource.<br>
  {{pagelink:Example-UKCore-Extension-ListWarningCode}}
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

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-List/~issues?level=File">Report Issue for UKCore-Li</a>.
</div>
</nocheck>

## Example Usage Scenarios ##
The following are example usage scenarios for the UK Core List profile:

- A list of allergies for a Patient
- A list of current medication for a Patient
- Record or update a list of information for Patient

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>List.status</code></td>
<td>Indicates the current state of this list.</td>
</tr>
<tr>
<td><code>List.code</code></td>
<td>This code defines the purpose of the list - why it was created.</td>
</tr>
<tr>
<td><code>List.subject</code></td>
<td>The common subject (or patient) of the resources that are in the list if there is one.</td>
</tr>
</table>

---