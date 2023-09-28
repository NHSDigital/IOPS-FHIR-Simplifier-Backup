# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-ServiceRequest?version=1.6.0">Profile UKCore-ServiceRequest</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/ServiceRequest.html">R5 Snapshot ServiceRequest</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">


<tr>
<td  class="comparison-fhir">ServiceRequest.code
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/r4/valueset<br><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/Terminology/AllValueSets/ValueSet-UKCore-ProcedureCode.page.md?version=current">UKCore-ProcedureCode</a> (preferred)</li>
</ul></td>
<td  class="comparison-fhir">ServiceRequest.code
<ul>
<li>0..1</li>
<li>CodeableReference (ActivityDefinition | PlanDefinition)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-procedure-code.html">procedure-code</a> (example)</li>
</ul></td>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Change from CodeableConcept to CodeableReference</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ServiceRequest.focus<ul>
<li>0..*</li>
<li>Reference (Any)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>


<tr>
<td  class="comparison-fhir">ServiceRequest.locationReference<ul>
<li>0..*</li>
<li>Reference (UKCore-Location)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ServiceRequest.location</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">ServiceRequest.locationCode<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/v3/ServiceDeliveryLocationRoleType/vs.html">ServiceDeliveryLocationRoleType</a> (example)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ServiceRequest.location</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ServiceRequest.location
<ul>
<li>0..*</li>
<li>CodeableReference (Location)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://terminology.hl7.org/4.0.0/ValueSet-v3-ServiceDeliveryLocationRoleType.html">ServiceDeliveryLocationRoleType</a> (example)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ServiceRequest.reasonCode<ul>
<li>0..*</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ServiceRequest.reason</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ServiceRequest.reasonReference<ul>
<li>0..*</li>
<li>Reference (UKCore-Condition | UKCore-DiagnosticReport | UKCore-DocumentReference | UKCore-Observation)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ServiceRequest.reason</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ServiceRequest.reason<ul>
<li>0..*</li>
<li>CodeableReference (Condition | DetectedIssue | DiagnosticReport | DocumentReference | Observation)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-procedure-reason.html">procedure-reason</a> (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ServiceRequest.bodyStructure<ul>
<li>0..1</li>
<li>Reference (BodyStructure)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>





</tbody>
</table>

