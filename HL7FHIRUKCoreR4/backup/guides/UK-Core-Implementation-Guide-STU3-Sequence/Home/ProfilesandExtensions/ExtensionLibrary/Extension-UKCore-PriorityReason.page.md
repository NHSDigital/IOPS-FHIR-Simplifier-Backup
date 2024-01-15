---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PriorityReason
---
## StructureDefinition Extension-UKCore-PriorityReason

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-ServiceRequest,text:ServiceRequest.priority}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Priority Reason</b> - An example to illustrate the priority reason extension, using a SNOMED CT concept, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-Extension-PriorityReason}}
<br><br>
  <b>Priority Reason</b> - An example to illustrate the priority reason extension, using a plain text reason, for a service request marked as urgent.<br>
{{pagelink:Example-UKCore-Extension-PriorityReason-SendingAsText}}
<br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-PriorityReason/~issues?level=File">Report Issue for Extension-UKCore-PriorityReason</a>.
</div>


<h3 id="guidance-priorityreason">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-ServiceRequestReasonCode}}.

---
