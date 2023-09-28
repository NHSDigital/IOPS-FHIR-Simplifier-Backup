## `{{page-title}}`

This is a backport from R5 to allow referencing to a Composition resource instance that provides structure for organizing the contents of the DiagnosticReport.

Note that the R5 element has the following rule that SHOULD be followed:

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Strength</th>
<th width="30%">Expression</th>
<th width="45%">Description</th>
</tr>
<tr>
<td>dgr-1</td>
<td>error</td>
<td>composition.exists() implies (composition.resolve().section.entry.reference.where(resolve() is Observation) in (result.reference|result.reference.resolve().hasMember.reference))</td>
<td>When a Composition is referenced in `Diagnostic.composition`, all Observation resources referenced in `Composition.entry` must also be referenced in `Diagnostic.entry` or in the references Observations in `Observation.hasMember`.</td>
</tr>
</table>