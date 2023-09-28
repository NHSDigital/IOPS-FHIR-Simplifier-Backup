## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>DocumentReference.status</code></td>
<td>The current status of the DocumentReference.</td>
</tr>
<tr>
<td><code>DocumentReference.intent</code></td>
<td>Indicates the "level" of actionability associated with the DocumentReference.</td>
</tr>
<tr>
<td><code>DocumentReference.code</code></td>
<td>A name or code (or both) briefly describing what the DocumentReference involves.</td>
</tr>
<tr>
<td><code>DocumentReference.focus</code></td>
<td>The request being actioned or the resource being manipulated by this DocumentReference.</td>
</tr>
<tr>
<td><code>DocumentReference.for</code></td>
<td>Beneficiary of the DocumentReference.</td>
</tr>
<tr>
<td><code>DocumentReference.authoredOn</code></td>
<td>DocumentReference creation date.</td>
</tr>
<tr>
<td><code>DocumentReference.requester</code></td>
<td>Who is asking for DocumentReference to be done.</td>
</tr>
<tr>
<td><code>DocumentReference.owner</code></td>
<td>Responsible individual.</td>
</tr>
<tr>
<td><code>DocumentReference.reasonCode</code></td>
<td>Why DocumentReference is needed.</td>
</tr>
<tr>
<td><code>DocumentReference.restriction</code></td>
<td>Constraints on fulfilment DocumentReferences.</td>
</tr>
<tr>
<td><code>DocumentReference.restriction.period</code></td>
<td>Over what time-period is fulfilment sought.
</td>
</tr>
<tr>
<td><code>DocumentReference.input</code></td>
<td>Information used to perform DocumentReference.</td>
</tr>
</table>

---