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

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core ServiceRequest-Lab profile:

- Query for ServiceRequest-Lab information
- Exchange ServiceRequest-Lab information used in Observations and DiagnosticReport

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
<td><code>ServiceRequest.status</code></td>
<td>The status of the order.</td>
</tr>
<tr>
<td><code>ServiceRequest.intent</code></td>
<td>Whether the request is a proposal, plan, an original order or a reflex order.</td>
</tr>
<tr>
<td><code>ServiceRequest.subject</code></td>
<td>Individual or Entity the service is ordered for.</td>
</tr>
<tr>
<td><code>ServiceRequest.authoredOn</code></td>
<td>Date request signed.</td>
</tr>
<tr>
<td><code>ServiceRequest.requester</code></td>
<td>Who/what is requesting service.</td>
</tr>
</table>
</div>

---