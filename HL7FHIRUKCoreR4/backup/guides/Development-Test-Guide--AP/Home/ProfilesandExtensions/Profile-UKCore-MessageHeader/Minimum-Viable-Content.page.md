## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>MessageHeader.event[x]</code></td>
<td>Code for the event this message represents or link to event definition</td>
</tr>
<tr>
<td><code>MessageHeader.destination</code></td>
<td>The destination application which the message is intended for.
</td>
</tr>
<tr>
<td><code>MessageHeader.sender</code></td>
<td>Real world sender of the message</td>
</tr>
<tr>
<td><code>MessageHeader.source</code></td>
<td>The source application from which this message originated.
</td>
</tr>
<tr>
<td><code>MessageHeader.focus</code></td>
<td>The actual content of the message</td>
</tr>
<table>

---