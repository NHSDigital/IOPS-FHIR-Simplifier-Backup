---
topic: Profile-Patient
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient
usage: http://hl7.org/fhir/StructureDefinition/Patient
issue: UKCore-Patient
---
# StructureDefinition-UKCore-Patient

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Address Key</b> - An example to illustrate the use of an address key used with the address datatype. </br>
{{pagelink:Example-UKCore-Extension-AddressKey}}   <br><br>

<b>Birth Sex</b> - An example to illustrate the extension for a patient's birth sex. </br>
{{pagelink:Example-UKCore-Extension-BirthSex}}   <br><br>

<b>Contact Rank</b> - An example to illustrate the extension for the patient's contact ranking. </br>
{{pagelink:Example-UKCore-Extension-ContactRank}}   <br><br>

<b>Contact Preference</b> - An example to illustrate the extension for a patient's contact preferences. </br>
{{pagelink:Example-UKCore-Extension-ContactPreference}}   <br><br>

<b>Copy Correspondence Indicator</b> - An Example to illustrate the extension for copy correspondence indicators. </br>
{{pagelink:Example-UKCore-Extension-CopyCorrespondenceIndicator}}   <br><br>

<b>Death Notification Status</b> - An example to illustrate the extension to indicate the death notification status of the patient. </br>
{{pagelink:Example-UKCore-Extension-DeathNotificationStatus}}   <br><br>

<b>Ethnic Category</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:Example-UKCore-Extension-EthnicCategory}}   <br><br>

<b>Melanie Jones</b> - An example of a baby patient. </br>
{{pagelink:Example-UKCore-Patient-BabyPatient}} <br><br>

<b>NHS Number Unavailable Reason</b>- An example of the extension which states the reason a patient's NHS number is unavailable.<br>
{{pagelink:Example-UKCore-Extension-NHSNumberUnavailableReason}} <br><br>

<b>NHS Number Verification Status</b> - An example of the extension which states the patient's NHS number verification status. </br>
{{pagelink:Example-UKCore-Extension-NHSNumberVerificationStatus}}   <br><br>

<b>Other Contact System</b> - An example to illustrate the extension to indicate other contact system(s) for a patient Richard Smith. </br>
{{pagelink:Example-UKCore-Extension-OtherContactSystem}}   <br><br>

<b>Residential Status</b> - An example to illustrate the extension to show the patient's residential status. </br>
{{pagelink:Example-UKCore-Extension-ResidentialStatus}}     <br><br> 

<b>Richard Smith</b> - An example to illustrate a male patient's demographics. </br>
{{pagelink:Example-UKCore-Patient-RichardSmith}}   <br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter `Patient.identifier` for a known NHS number.
- Query for Patient demographic information using query parameters such as `Patient.name.family`, `Patient.name.given`, `Patient.birthDate`, and `Patient.gender`.
- Exchange Patient demographic information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Patient.identifier</code></td>
<td>An identifier for this patient.</td>
</tr>
<tr>
<td><code>Patient.identifier.system</code></td>
<td>The namespace for the identifier value.</td>
</tr>
<tr>
<td><code>Patient.identifier.value</code></td>
<td>The portion of the identifier typically relevant to the user and which is unique within the context of the system.</td>
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
<td><code>Patient.name.family</code></td>
<td>Family name (often called 'Surname').</td>
</tr>
<tr>
<td><code>Patient.name.given</code></td>
<td>Given names (not always 'first'). Includes middle names.</td>
</tr>
<tr>
<td><code>Patient.telecom</code></td>
<td>A contact detail for the individual</td>
</tr>
<tr>
<td><code>Patient.telecom.system</code></td>
<td>Telecommunications form for contact point</td>
</tr>
<tr>
<td><code>Patient.telecom.value</code></td>
<td>The actual contact point details</td>
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
<td>An address for the individual
</td>
</tr>
<tr>
<td><code>Patient.address.line</code></td>
<td>Street name, number, direction & P.O. Box etc.</td>
</tr>
<tr>
<td><code>Patient.address.city</code></td>
<td>Name of city, town etc.</td>
</tr>
<tr>
<td><code>Patient.address.postalCode</code></td>
<td>Postal code for area</td>
</tr>
</table>
</div>

---
