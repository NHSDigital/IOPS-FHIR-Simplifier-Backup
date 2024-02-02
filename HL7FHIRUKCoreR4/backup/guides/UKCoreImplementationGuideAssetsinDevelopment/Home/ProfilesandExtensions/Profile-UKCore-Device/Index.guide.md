---
topic: Profile-Device
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Device
usage: http://hl7.org/fhir/StructureDefinition/Device
issue: UKCore-Device
---

# StructureDefinition-UKCore-Device

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Colostomy Bag</b> - An example to illustrate a colostomy bag<br/>
{{pagelink:Example-UKCore-Device-ColostomyBag}}
<b>Software as a Medical Device</b> - An example to illustrate recording AI softweare as a medical device.<br/>
{{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}<br><br>
<b>Sphygmomanometer</b> - An example to illustrate recording a specific blood pressure device.<br/>
{{pagelink:Example-UKCore-Device-Sphygmomanometer}}<br><br>

</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Device profile:

- Query and retrieve information regarding a medical device
- Record or update a device used during a patients care


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
<td><code>Device.status</code></td>
<td>The status of the Device.</td>
</tr>
<tr>
<td><code>Device.type</code></td>
<td>The type of the Device.</td>
</tr>
</table>
</div>

---
