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


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core HealthcareService profile:
- Query for details of a healthcare service
- Exchange healthcare service information within a FHIR document or message.

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
<td><code>HealthcareService.providedBy</code></td>
<td>The organization that provides this healthcare service.</td>
</tr>
<tr>
<td><code>HealthcareService.type</code></td>
<td>The type of service provided by this healthcare service.</td>
</tr>
</table>
</div>

---
