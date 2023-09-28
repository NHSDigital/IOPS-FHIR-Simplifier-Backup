---
topic: Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c
---
# StructureDefinition-UKCore-Patient

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/patient.html" target="_blank">Patient</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve an individual’s demographic information.

## Profile Purpose
This profile allows exchange of demographics and other administrative information about an individual receiving care or other health-related services.

<div class="tab">
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
{{pagelink:ExampleUKCore-Patient-BabyPatient}}
<br><br>
<b>Ethnic Category</b> - An example to illustrate patient Ethnic Category information. </br>
{{pagelink:ExampleUKCore-Patient-Extension-EthnicCategory}}   <br><br>
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
{{pagelink:Example-UKCore-Patient-Extension-ContactPreference-duplicate-2}}   
<br><br>
<b>Copy Correspondence Indicator</b> - An Example to illustrate the extension for copy correspondence indicators. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-CopyCorrespondenceIndicator-duplicate-2}}   
<br><br>
<b>Death Notification Status</b> - An example to illustrate the extension to indicate the death notification status of the patient. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-DeathNotificationStatus}}   
<br><br>
<b>Other Contact System</b> - An example to illustrate the extension to indicate other contact system(s) for a patient Richard Smith. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-OtherContactSystem}}   
<br><br>
<b>NHS Number Verification Status</b> - An example of the extension which states the patient's NHS number verification status. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-NHSNumberVerificationStatus}}   
<br><br>
<b>Residential Status</b> - An example to illustrate the extension to show the patient's residential status. 
</br>
{{pagelink:Example-UKCore-Patient-Extension-ResidentialStatus}}   
<br><br>

</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter `Patient.identifier` for a known NHS number.
- Query for Patient demographic information using query parameters such as `name.family`, `name.given`, `birthDate`, and `gender`.
- Exchange Patient demographic information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Minimal Viable Content

A minimum viable content that all provider and consumer systems SHOULD support are the following elements.

<table id="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>identifier, name</code></td>
<td>As a minimum either a <code>Patient.identifier</code> or <code>Patient.name</code> SHOULD be provided.</td>
</tr>
</table>
<br>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important:</h4>
When <code>Patient.identifier:nhsNumber</code> is populated  <code>Patient.identifier:nhsNumber.extension:nhsNumberVerificationStatus</code>
SHOULD also be populated.
</div>






---
