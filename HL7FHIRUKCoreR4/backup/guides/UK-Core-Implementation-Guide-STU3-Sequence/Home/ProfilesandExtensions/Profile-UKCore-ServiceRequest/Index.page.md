---
topic: Profile-ServiceRequest
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest
usage: http://hl7.org/fhir/StructureDefinition/ServiceRequest
issue: UKCore-ServiceRequest
---
# StructureDefinition-UKCore-ServiceRequest

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
   <b>Additional Contact</b> - An example to illustrate providing an additional contact with a service request.<br>
{{pagelink:Example-UKCore-Extension-AdditionalContact}}
<br><br>
  <b>Colonoscopy Request</b> - An example to illustrate a service request regarding a colonoscopy.<br/>
{{pagelink:Example-UKCore-ServiceRequest-ColonoscopyRequest}}
<br><br>
<b>Coverage</b> - An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
{{pagelink:Example-UKCore-Extension-Coverage}}
<br/><br/>
<b>Priority Reason</b> - An example to illustrate the priority reason extension, using a SNOMED CT concept, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-Extension-PriorityReason}}
<br><br>
  <b>Priority Reason</b> - An example to illustrate the priority reason extension, using a plain text reason, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-Extension-PriorityReason-SendingAsText}}
<br><br>
<b>Source of Service Request</b> - An example to illustrate the source of service request extension associated with a service request.<br/>
{{pagelink:Example-UKCore-Extension-SourceOfServiceRequest}}
<br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core ServiceRequest profile:
- Query for service request information for a given Patient
- Exchange service request information within a FHIR document or message.

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
<td><code>ServiceRequest.basedOn</code></td>
<td>What request fulfills.</td>
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
<td><code>ServiceRequest.category</code></td>
<td>A code that classifies the service for searching, sorting and display purposes.</td>
</tr>
<tr>
<td><code>ServiceRequest.priority</code></td>
<td>Indicates how quickly the ServiceRequest should be addressed with respect to other requests.</td>
</tr>
<tr>
<td><code>ServiceRequest.code</code></td>
<td>What is being requested/ordered.</td>
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