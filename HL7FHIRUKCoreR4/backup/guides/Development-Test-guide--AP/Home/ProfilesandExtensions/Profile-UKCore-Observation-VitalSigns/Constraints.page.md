## Constraints (differential)

More information about the constraints on the <code>UKCore-Observation-VitalSigns</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width15">Severity</th>
<th class="width30">Expression</th>
<th class="width40">Human Description</th>
</tr>
<tr>
<td>ukcore-obs-vs-001</td>
<td>error</td>
<td>
<code><code>code.coding</code>.where(<code>system</code>='http://loinc.org').exists()
</td>
<td>Observation.code.coding SHALL include a LOINC "magic code"</td>
</tr>
</table>

<hr class="thickline">