# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Consent?version=1.6.0">Profile UKCore-Consent</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/Consent.html">R5 Snapshot Consent</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">


<tr>
<td  class="comparison-fhir">Consent.scope
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-scope.html">consent-scope</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>CodeSystem incorporated into Consent.category</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.category
<ul>
<li>1..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-category.html">consent-category</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.category
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="http://hl7.org/fhir/5.0.0-snapshot3/valueset-consent-category.html">consent-category</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Minimum cardinality changed from 1 to 0 in R5</li>
<li>CodeSystem <code>http://terminology.hl7.org/CodeSystem/consentscope</code> added to R5 ValueSet</li>
<li>Binding strength changed from extensible to example in R5</li>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.patient<ul>
<li>0..1</li>
<li>Reference (UKCore-Patient)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.subject</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.subject<ul>
<li>0..1</li>
<li>Reference (Patient | Practitioner | Group)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.dateTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.date</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.date<ul>
<li>0..1</li>
<li>date</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.period<ul>
<li>0..1</li>
<li>Period</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">Consent.performer<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-PractitionerRole | UKCore-RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.grantor and Consent.grantee</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.grantor<ul>
<li>0..1</li>
<li>Reference (CareTeam | HealthcareService | Organization | Patient | Practitioner | PractitionerRole | RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5.</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.grantee<ul>
<li>0..1</li>
<li>Reference (CareTeam | HealthcareService | Organization | Patient | Practitioner | PractitionerRole | RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5.</li>
</tr>

<tr>
<td  class="comparison-fhir">Consent.organization<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.manager</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.manager<ul>
<li>0..1</li>
<li>Reference (HealthcareService | Organization | Patient | Practitioner)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.controller<ul>
<li>0..1</li>
<li>Reference (HealthcareService | Organization | Patient | Practitioner)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">Consent.source[x]<ul>
<li>0..1</li>
<li>Attachment<br>
Reference (UKCore-Consent | Contract | UKCore-DocumentReference | UKCore-QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.sourceAttachment and Consent.sourceReference</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.sourceAttachment<ul>
<li>0..*</li>
<li>Attachment</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.sourceReference<ul>
<li>0..*</li>
<li>Reference (Consent | Contract | DocumentReference | QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.policy<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.policyRule<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-consent-policy.html">consent-policy</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by Consent.regulatoryBasis</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.regulatoryBasis<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-consent-policy.html">consent-policy</a> (extensible)</li>
</ul>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.policyBasis<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.policyText<ul>
<li>0..*</li>
<li>Reference (DocumentReference)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.verification<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.verification<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
<td  class="comparison-note">
<ul>
<li><b>New sub elements in R5:</b> </li>
<li>Consent.verification.verificationType, 0..1, <a href="http://hl7.org/fhir/5.0.0-snapshot3/valueset-consent-verification.html">consent-verification</a> (example)</li>
<li>Consent.verification.verifiedBy, 0..1, Reference (Organization | Practitioner | PractitionerRole)</li>
<li><b>Max cardinality change in R5:</b></li>
<li>Consent.verification.verificationDate, was 0..1, now 0..*</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.provision<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.provision<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li><b>Removed sub elements in R5:</b> </li>
<li>Consent.provision.class</li>
<li><b>New sub elements in R5:</b> </li>
<li>Consent.provision.documentType, 0..1, <a href="http://hl7.org/fhir/5.0.0-snapshot3/valueset-consent-content-class.html">consent-content-class</a> (preferred)</li>
<li>Consent.provision.resourceType, 0..1, <a href="http://hl7.org/fhir/5.0.0-snapshot3/valueset-resource-types.html">resource-types</a> (extensible)</li>
<li>Consent.provision.expression, 0..1, Expression</li>
<li><b>Min cardinality change in R5:</b></li>
<li>Consent.provision.actor.role, was 1..1, now 0..1</li>
<li>Consent.provision.actor.reference, was 1..1, now 0..1</li>
<li><b>Binding change in R5:</b></li>
<li>Consent.provision.actor.role</li>
<li>Consent.provision.securityLabel</li>
<li><b>Modifier change in R5:</b></li>
<li>Consent.provision.type</li>
</ul>
</td>
</tr>

</tbody>
</table>

