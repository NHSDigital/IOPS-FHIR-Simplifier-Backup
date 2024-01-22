---
topic: Profile-HealthcareService
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-HealthcareService
usage: http://hl7.org/fhir/StructureDefinition/HealthcareService
issue: UKCore-HealthcareService
---
# StructureDefinition-UKCore-HealthcareService

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Orthopaedic Service</b> - An example to illustrate information about an orthopaedic service within a HealthcareService resource. <br>
{{pagelink:Example-UKCore-HealthcareService-OrthopaedicService}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core HealthcareService profile:
- Query for details of a healthcare service
- Exchange healthcare service information within a FHIR document or message.

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
<td><code>HealthcareService.providedBy</code></td>
<td>The organization that provides this healthcare service.</td>
</tr>
</table>

---
