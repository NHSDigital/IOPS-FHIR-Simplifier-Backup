## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Consent.status</code></td>
<td>Indicates the current state of this consent.</td>
</tr>
<tr>
<td><code>Consent.scope</code></td>
<td>A selector of the type of consent being presented: ADR, Privacy, Treatment, Research.</td>
</tr>
<tr>
<td><code>Consent.category</code></td>
<td>The classification of the consent statement - for indexing/retrieval</td>
</tr>
<tr>
<td><code>Consent.patient</code></td>
<td>The patient/healthcare consumer to whom this consent applies.
</td>
</tr>
<tr>
<td><code>Consent.dateTime</code></td>
<td>When this consent was issued / created / indexed.
</td>
</tr>
<tr>
<td><code>Consent.performer</code></td>
<td>Who is agreeing to the policy and rules</td>
</tr>
<tr>
<td><code>Consent.organization</code></td>
<td>The custodian of the consent</td>
</tr>
<tr>
<td><code>Consent.source[x]</code></td>
<td>The source from which this consent is taken</td>
</tr>
</table>

---
