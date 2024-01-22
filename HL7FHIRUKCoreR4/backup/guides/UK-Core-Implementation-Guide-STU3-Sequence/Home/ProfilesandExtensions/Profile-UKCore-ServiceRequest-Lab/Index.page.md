---
topic: Profile-ServiceRequest-Lab
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest-Lab
usage: http://hl7.org/fhir/StructureDefinition/ServiceRequest
issue: UKCore-serviceRequest-Lab
---
# StructureDefinition-UKCore-ServiceRequest-Lab

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>C Reactive Protein Request</b> - An example to illustrate a request for a C Reactive Protein test based on an inflammed finger joint observation.<br>
{{pagelink:Example-UKCore-ServiceRequest-Lab-CReactiveProtein}}
<br><br>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core ServiceRequest-Lab profile:

- Query for ServiceRequest-Lab information
- Exchange ServiceRequest-Lab information used in Observations and DiagnosticReport

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}} table, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>ServiceRequest.reasonReference</code></td>
<td>Explanation / Justification for for why this service is being requested.</td>
</tr>
</table>

---