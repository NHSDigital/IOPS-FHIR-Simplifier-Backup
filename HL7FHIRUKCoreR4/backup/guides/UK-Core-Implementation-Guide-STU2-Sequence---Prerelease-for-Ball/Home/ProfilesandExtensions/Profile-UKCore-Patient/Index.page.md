---
topic: Profile-Patient-88961
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
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
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
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter `Patient.identifier` for a known NHS number.
- Query for Patient demographic information using query parameters such as `Patient.name.family`, `Patient.name.given`, `Patient.birthDate`, and `Patient.gender`.
- Exchange Patient demographic information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Patient.identifier</code></td>
<td>An identifier for this patient.</td>
</tr>
<tr>
<td><code>Patient.active</code></td>
<td>Whether this patient's record is in active use.</td>
</tr>
<tr>
<td><code>Patient.name</code></td>
<td>A name associated with the patient.</td>
</tr>
<tr>
<td><code>Patient.telecom</code></td>
<td>A contact detail for the individual</td>
</tr>
<tr>
<td><code>Patient.gender</code></td>
<td> the gender that the patient is considered to have for administration and record keeping purposes.</td>
</tr>
<tr>
<td><code>Patient.birthDate</code></td>
<td>The date of birth for the individual.</td>
</tr>
<tr>
<td><code>Patient.address</code></td>
<td>An address for the individual</td>
</tr>
</table>

---
