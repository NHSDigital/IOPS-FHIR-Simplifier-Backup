---
topic: Profile-Location
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location
usage: http://hl7.org/fhir/StructureDefinition/Location
issue: UKCore-Location
---
# StructureDefinition-UKCore-Location

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>SJUH Location</b> -  An example to illustrate a Cardiology department in a hospital<br/>
{{pagelink:Example-UKCore-Location-CardiologySJUH}}
 <br><br>
 <b>General Practice Nurse Clinic location</b> - An example to illustrate a General Practice Nurse Clinic<br/>
 {{pagelink:Example-UKCore-Location-GeneralPracticeNurseClinic}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UKCore Location profile:

- To describe care locations such as hospital wards
- To describe locations where patient care has or may take place, including scenes of accidents like by the side of a road.

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
<td><code>Location.identifier:odsSiteCode</code></td>
<td>ODS Site code to identify the organisation at site level.</td>
</tr>
<tr>
<td><code>Location.status</code></td>
<td>Is the location active, inactive, or suspended</td>
</tr>
<tr>
<td><code>Location.name</code></td>
<td>Name of the location as used by humans. This does not need to be unique.</td>
</tr>
<tr>
<td><code>Location.address</code></td>
<td>If locations can be visited, we need to keep track of their address.</td>
</tr>
</table>
</div>

---