## Constraints (differential)

More information about the constraints on the <code>UKCore-Immunization</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width15">Severity</th>
<th class="width30">Expression</th>
<th class="width40">Human Description</th>
</tr>
<tr>
<td>ukcore-imm-001</td>
<td>error</td>
<td>(<code>status</code> != 'not-done') or <br>(<code>status</code> = 'not-done' and <code>statusReason</code>.exists())</td>
<td>If the immunization was not given then<br><code>Immunization.status</code> value SHALL = 'not-done',<br>and the <code> Immunization.statusReason</code> SHALL be populated</td>
</tr>
</table>

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The key for this constraint was changed from <code>ukcore-imm-1</code> in UK Core STU1 Sequence, to <code>ukcore-imm-001</code> in this release, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div> 

---