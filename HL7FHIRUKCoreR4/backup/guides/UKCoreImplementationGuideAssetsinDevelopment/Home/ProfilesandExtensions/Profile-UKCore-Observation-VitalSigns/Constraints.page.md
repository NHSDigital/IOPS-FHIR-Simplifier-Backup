## Constraints (differential)

More information about the constraints on the <code>UKCore-Observation-VitalSigns</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>ukcore-obs-vs-001</td>
<td>error</td>
<td>
<code>category</code>.where(<code>code</code>='vital-signs').exists() implies <code>code.coding</code>.where(<code>system</code>='http://loinc.org').exists()
</td>
<td>Where the category is Vital Signs the code.coding SHALL include a LOINC "magic code"</td>
</tr>
</table>

<hr class="thickline">