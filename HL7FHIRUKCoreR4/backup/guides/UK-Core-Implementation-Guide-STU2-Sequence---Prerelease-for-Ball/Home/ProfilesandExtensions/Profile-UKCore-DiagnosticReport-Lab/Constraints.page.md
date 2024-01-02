## Constraints (differential)

More information about the constraints on the <code>UKCore-DiagnosticReport-Lab</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>ukcore-diag-lab-001</td>
<td>warning</td>
<td>
<code>issued</code>.exists() or (<code>issued</code>.empty() and (<code>status</code> in ('partial' | 'preliminary' | 'final' | 'amended' | 'corrected' | 'appended')).not())
</td>
<td>An issued time SHOULD be present if <code>status</code> = partial, preliminary, final, amended, corrected or appended.</td>
</tr>
</table>

---