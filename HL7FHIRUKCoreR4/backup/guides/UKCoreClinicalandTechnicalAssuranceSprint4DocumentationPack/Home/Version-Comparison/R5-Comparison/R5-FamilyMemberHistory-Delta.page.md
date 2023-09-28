# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-FamilyMemberHistory?version=1.6.0">Profile UKCore-FamilyMemberHistory</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/FamilyMemberHistory.html">R5 Snapshot FamilyMemberHistory</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">



<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">FamilyMemberHistory.participant
<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">FamilyMemberHistory.reason<ul>
<li>0..*</li>
<li>CodeableReference (Condition | Observation | AllergyIntolerance | QuestionnaireResponse | DiagnosticReport | DocumentReference)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-clinical-findings.html">clinical-findings</a> (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">FamilyMemberHistory.procedure
<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">FamilyMemberHistory.reasonCode<ul>
<li>0..*</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by FamilyMemberHistory.reason</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">FamilyMemberHistory.reasonReference<ul>
<li>0..*</li>
<li>Reference (UKCore-AllergyIntolerance | UKCore-Condition | UKCore-DiagnosticReport | UKCore-DocumentReference | UKCore-Observation | UKCore-QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by FamilyMemberHistory.reason</li>
</ul>
</td>
</tr>

</tbody>
</table>

