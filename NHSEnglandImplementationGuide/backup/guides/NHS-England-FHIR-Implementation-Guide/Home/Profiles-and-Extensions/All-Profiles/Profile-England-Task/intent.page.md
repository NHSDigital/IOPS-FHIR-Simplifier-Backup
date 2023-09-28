## `intent`

<table class="regular assets">
<tr>
<td>Element Id</td>
<td>Task.intent</td>
</tr>
<tr>
<td> <a href='https://www.hl7.org/fhir/conformance-rules.html#cardinality' target="_blank">Cardinality</a></td>
<td> 1..1</td>
</tr>
<tr>
<td> <a href='"https://www.hl7.org/fhir/terminologies.html' target="_blank">Terminology Binding</a></td>
<td> <a href='https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/81355' target="_blank">TaskIntent</a> (Required)<br>Distinguishes whether the task is a proposal, plan or full order. </td>
</tr>
<tr>
<td> <a href='https://www.hl7.org/fhir/datatypes.html' target="_blank">type</a></td>
<td> <a href='https://www.hl7.org/fhir/datatypes.html#code' target="_blank">code</a></td>
</tr>
</table>

<br/>
 <b> Definition </b><Br>

 Indicates the "level" of actionability associated with the Task, i.e. i+R[9]Cs this a proposed task, a planned task, an actionable task, etc.

 <b>Comment</b><br>

 Is not processed by EPS and is included for FHIR compliance reasons. The value should always be `order`.

---