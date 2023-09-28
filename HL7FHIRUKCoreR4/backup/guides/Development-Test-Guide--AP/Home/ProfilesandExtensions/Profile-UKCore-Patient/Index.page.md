---
topic: Profile-Patient
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient
---
# StructureDefinition-UKCore-Patient

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCorePatient'
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
	name = 'UKCorePatient'
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
<b>Richard Smith</b> - An example to illustrate a male patient's demographics. 
</br>
{{pagelink:Example-UKCore-Patient-RichardSmith}}   
<br><br>
<b>Melanie Jones</b> - An example of a baby patient. </br>
{{pagelink:Example-UKCore-Patient-BabyPatient}}
<br><br>
<b>Ethnic Category</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:Example-UKCore-Patient-Extension-EthnicCategory}}   <br><br>
<b>Address Key</b> - An example to illustrate the use of an address key used with the address datatype. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-AddressKey}}   
<br><br>
<b>Birth Sex</b> - An example to illustrate the extension for a patient's birth sex. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-BirthSex}}   
<br><br>
<b>Contact Rank</b> - An example to illustrate the extension for the patient's contact ranking. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-ContactRank}}   
<br><br>
<b>Contact Preference</b> - An example to illustrate the extension for a patient's contact preferences. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-ContactPreference}}   
<br><br>
<b>Copy Correspondence Indicator</b> - An Example to illustrate the extension for copy correspondence indicators. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-CopyCorrespondenceIndicator}}   
<br><br>
<b>Death Notification Status</b> - An example to illustrate the extension to indicate the death notification status of the patient. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-DeathNotificationStatus}}   
<br><br>
<b>Other Contact System</b> - An example to illustrate the extension to indicate other contact system(s) for a patient Richard Smith. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-OtherContactSystem}}   
<br><br>
<b>NHS Number Unavailable Reason</b>- An example of the extension which states the reason a patient's NHS number is unavailable.<br>
{{pagelink:Example-UKCore-Patient-Extension-NHSNumberUnavailableReason}}
<br><br>
<b>NHS Number Verification Status</b> - An example of the extension which states the patient's NHS number verification status. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-NHSNumberVerificationStatus}}   
<br><br>
<b>Residential Status</b> - An example to illustrate the extension to show the patient's residential status. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-ResidentialStatus}}   
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter `Patient.identifier` for a known NHS number.
- Query for Patient demographic information using query parameters such as `Patient.name.family`, `Patient.name.given`, `Patient.birthDate`, and `Patient.gender`.
- Exchange Patient demographic information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

