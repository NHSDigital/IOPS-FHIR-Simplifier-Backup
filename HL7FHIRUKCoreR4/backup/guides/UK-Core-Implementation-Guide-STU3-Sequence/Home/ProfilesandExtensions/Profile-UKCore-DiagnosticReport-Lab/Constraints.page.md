## Constraints (differential)

More information about the constraints on the <code>UKCore-DiagnosticReport-Lab</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width10">Severity</th>
<th class="width30">Expression</th>
<th class="width45">Human Description</th>
</tr>
<tr>
<td>ukcore-diag-lab-001</td>
<td>warning</td>
<td>
<code>effective</code>.exists() or (<code>effective</code>.empty() and (<code>status</code> in ('partial' | 'preliminary' | 'final' | 'amended' | 'corrected' | 'appended')).not())
</td>
<td>An effective time SHOULD be present if <code>status</code> = partial, preliminary, final, amended, corrected or appended.</td>
</tr>
</table>

---