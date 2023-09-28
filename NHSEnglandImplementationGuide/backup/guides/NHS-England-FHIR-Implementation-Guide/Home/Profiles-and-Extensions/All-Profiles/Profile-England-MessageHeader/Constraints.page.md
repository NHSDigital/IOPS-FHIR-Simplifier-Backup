## Constraints (differential)

More information about the constraints on the <code>England-MessageHeader</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-meh-001</td>
<td>warning</td>
<td>event.code.where(substring($this.length()-6) = &#39;update&#39;).exists().not() or (event.code.where(substring($this.length()-6) = &#39;update&#39;).exists() and extension(&#39;https://fhir.nhs.uk/StructureDefinition/Extension-England-MessageHeaderReplacement&#39;).exists())</td>
<td>replacementOf extension is required for update messages</td>
</tr>
</table>

---