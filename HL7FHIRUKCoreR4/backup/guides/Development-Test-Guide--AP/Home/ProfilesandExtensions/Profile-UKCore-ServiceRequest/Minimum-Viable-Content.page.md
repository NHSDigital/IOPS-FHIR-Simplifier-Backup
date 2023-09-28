## Minimum Viable Content

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