## {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://www.hl7.org/fhir/R4/familymemberhistory.html">Base R4 FamilyMemberHistory</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-FamilyMemberHistory?version=1.6.0">Profile UKCore-FamilyMemberHistory</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-FamilyMemberHistory.guide.md?version=current">CareConnect-FamilyMemberHistory-1</a></th>
<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<tr>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">FamilyMemberHistory.definition
<ul>
<li>0..*</li>
<li>canonical(PlanDefinition | Questionnaire)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Deleted in R4</li>
<li>Replaced with FamilyMemberHistory.instantiatesCanonical </li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.instantiatesCanonical
<ul>
<li>0..*</li>
<li>canonical(PlanDefinition | Questionnaire | ActivityDefinition | Measure | OperationDefinition)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.instantiatesCanonical
<ul>
<li>0..*</li>
<li>canonical(PlanDefinition | UKCore Questionnaire | ActivityDefinition | Measure | OperationDefinition)</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>New Element in R4</li>
<li>Replaces FamilyMemberHistory.definition </li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.instantiatesUri
<ul>
<li>0..*</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.instantiatesUri
<ul>
<li>0..*</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>New Element in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/FHIR/r4/valueset-history-status.html">history-status</a> (required)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/FHIR/r4/valueset-history-status.html">history-status</a> (required)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/ValueSet/<br>history-status(required)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Change value set from<br>http://hl7.org/fhir/ValueSet/history-status|3.0.2<br>to<br> http://hl7.org/fhir/ValueSet/history-status|4.0.1</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">FamilyMemberHistory.notDone
<ul>
<li>0..1</li>
<li>boolean</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Deleted in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">FamilyMemberHistory.notDoneReason
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Deleted in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.dataAbsentReason
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.dataAbsentReason
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>New Element in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.relationship
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://terminology.hl7.org/ValueSet<br><a href="https://terminology.hl7.org/5.0.0/ValueSet-v3-RoleCode.html">v3-RoleCode</a> (example)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.relationship
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://terminology.hl7.org/ValueSet<br><a href="https://terminology.hl7.org/5.0.0/ValueSet-v3-RoleCode.html">v3-RoleCode</a> (example)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.relationship
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/ValueSet/<br>v3-RoleCode(example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Change value set from<br>http://hl7.org/fhir/ValueSet/v3-RoleCode<br>to<br> http://terminology.hl7.org/ValueSet/v3-RoleCode</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-fhir">FamilyMemberHistory.gender
<ul>
<li>0..1</li>
<li>code</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Deleted in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.sex
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.sex
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>New Element in R4</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.estimateAge
<ul>
<li>0..1</li>
<li>boolean</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.estimateAge
<ul>
<li>0..1</li>
<li>boolean</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>No longer marked as Modifier</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.reasonReference
<ul>
<li>0..*</li>
<li>Reference (Condition | Observation | AllergyIntolerance | QuestionnaireResponse | DiagnosticReport | DocumentReference)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.reasonReference
<ul>
<li>0..*</li>
<li>Reference (UKCore-Condition | UKCore-Observation |UKCore-AllergyIntolerance | UKCore-QuestionnaireResponse | UKCore-DiagnosticReport | UKCore-DocumentReference)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.reasonReference
<ul>
<li>0..*</li>
<li>Reference (QuestionnaireResponse | CareConnect-Observation-1 | CareConnect-Condition-1 | CareConnect-AllergyIntolerance-1)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added target reference to <em>DiagnosticReport</em> and <em>DocumentReference</em> in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.note.authorReference
<ul>
<li>0..1</li>
<li>Reference (Practitioner | Patient | RelatedPerson | Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.note.authorReference
<ul>
<li>0..1</li>
<li>Reference (UKCore-Practitioner | UKCore-Patient |UKCore-RelatedPerson | UKCore-Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.note.authorReference
<ul>
<li>0..1</li>
<li>Reference (CareConnect-Patient-1 | CareConnect-Practitioner-1 | CareConnect-RelatedPerson-1)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added target reference to <em>Organization</em> in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">FamilyMemberHistory.condition.contributedToDeath
<ul>
<li>0..1</li>
<li>boolean</li>
</ul>
</td>
<td  class="comparison-fhir">FamilyMemberHistory.condition.contributedToDeath
<ul>
<li>0..1</li>
<li>boolean</li>
</ul>
</td>
<td  class="comparison-fhir">
</td>
<td  class="comparison-note">
<ul>
<li>New Element in R4</li>
</ul>
</td>
</tr>

</tbody>
</table>