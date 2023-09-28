---
topic: Profile-ServiceRequest-88746
---
# StructureDefinition-UKCore-ServiceRequest

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 5 and Sprint 6, for different use cases. This is a new Profile added to UK Core and undergoing review in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreServiceRequest'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'UKCoreServiceRequest'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
    <b>Additional Contact</b> - An example to illustrate providing an additional contact with a service request.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-AdditionalContact}}
<br><br>
  <b>Colonoscopy Request</b> - An example to illustrate a service request regarding a colonoscopy.<br/>
{{pagelink:Example-UKCore-ServiceRequest-ColonoscopyRequest}}
<br><br>
<b>Coverage</b> - An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-Coverage}}
<br/><br/>
<b>Priority Reason</b> - An example to illustrate the priority reason extension, using a SNOMED CT concept, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-PriorityReason}}
<br><br>
  <b>Priority Reason</b> - An example to illustrate the priority reason extension, using a plain text reason, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-PriorityReason-PlainText}}
<br><br>
<b>Source of Service Request</b> - An example to illustrate the source of service request extension associated with a service request.<br/>
{{pagelink:Example-UKCore-ServiceRequest-Extension-SourceOfServiceRequest}}
<br><br>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core ServiceRequest profile:
- Query for service request information for a given Patient
- Exchange service request information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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

---