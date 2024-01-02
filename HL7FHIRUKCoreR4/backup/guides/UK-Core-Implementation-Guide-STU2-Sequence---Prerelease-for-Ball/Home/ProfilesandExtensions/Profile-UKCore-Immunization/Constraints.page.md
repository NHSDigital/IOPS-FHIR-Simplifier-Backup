## Constraints (differential)

More information about the constraints on the <code>UKCore-Immunization</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>ukcore-imm-001</td>
<td>error</td>
<td>(<code>status</code> != 'not-done') or <br>(<code>status</code> = 'not-done' and <code>statusReason</code>.exists())</td>
<td>If the immunization was not given then<br><code>Immunization.status</code> value SHALL = 'not-done',<br>and the <code> Immunization.statusReason</code> SHALL be populated</td>
</tr>
</table>

---