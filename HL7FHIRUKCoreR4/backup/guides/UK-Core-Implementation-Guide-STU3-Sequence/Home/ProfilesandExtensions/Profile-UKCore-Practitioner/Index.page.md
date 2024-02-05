---
topic: Profile-Practitioner
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner
usage: http://hl7.org/fhir/StructureDefinition/Practitioner
issue: UKCore-Practitioner
---
# StructureDefinition-UKCore-Practitioner

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>General Practitioner</b> - An example to illustrate a practitioner who is the Patient's GP. 
<br>
{{pagelink:Example-UKCore-Practitioner-DoctorPaulRastall}}
<br><br>
<b>Consultant</b> - An example to illustrate a practitioner who is a Consultant. 
<br>
{{pagelink:Example-UKCore-Practitioner-ConsultantSandraGose}}
<br><br>
<b>Pharmacist</b> - An example to illustrate a practitioner who is a Pharmacist.
<br>
{{pagelink:Example-UKCore-Practitioner-PharmacistJimmyChuck}}
<br><br>
Note: the practitioner's role information is carried in the {{pagelink:Profile-PractitionerRole}}   <br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Practitioner profile:

- Query for practitioner information using the query parameter identifier (`Practitioner.identifier`) for a known SDS User Identifier.
- Exchange practitioner information within a FHIR document or message.

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
<td><code>Practitioner.identifier</code></td>
<td>An identifier that applies to this person in this role.
</td>
</tr>
<tr>
<td><code>Practitioner.name</code></td>
<td>The name(s) associated with the practitioner</td>
</tr>
<tr>
<td><code>Practitioner.name.family</code></td>
<td>Family name (often called 'Surname')</td>
</tr>
<tr>
<td><code>Practitioner.telecom</code></td>
<td>A contact detail for the practitioner (that apply to all roles)</td>
</tr>
</table>
</div>

---