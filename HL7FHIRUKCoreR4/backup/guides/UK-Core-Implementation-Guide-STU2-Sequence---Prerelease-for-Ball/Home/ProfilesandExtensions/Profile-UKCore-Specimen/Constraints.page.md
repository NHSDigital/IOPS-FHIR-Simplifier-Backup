## Constraints (differential)

More information about the constraints on the <code>UKCore-Specimen</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>ukcore-spec-001</td>
<td>error</td>
<td>collection.collector.reference.empty() or collection.collector.extension(&#39;http://hl7.org/fhir/5.0/StructureDefinition/extension-Specimen.collection.collector&#39;).empty()</td>
<td>There SHALL be only one reference between <code>collection.collector</code> and the extension <code>collectionCollectorR5</code></td>
</tr>
</table>

---