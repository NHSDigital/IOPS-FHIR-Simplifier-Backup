# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/R4/Consent.html">Base R4 Consent</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Consent?version=1.6.0">Profile UKCore-Consent</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-Consent.guide.md?version=current">CareConnect-Consent-1</a></th>
<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<tr>
<td  class="comparison-fhir">Consent.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-state-codes.html">consent-state-codes</a> (required)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-state-codes.html">consent-state-codes</a> (required)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/ValueSet/<br>consent-state-codes(required)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Change value set from<br>http://hl7.org/fhir/ValueSet/consent-state-codes<br>to<br> http://hl7.org/fhir/ValueSet/consent-state-codes|4.0.1</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.scope
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-scope.html">consent-scope</a> (extensible)</li>
</ul>
</td>
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
<li>New element in R4.</li>
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
<li>1..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-consent-category.html">consent-category</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.category
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/ValueSet/<br>consent-category (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Minimum cardinality changed from 0 to 1 in R4.</li>
<li>CodeSystem http://hl7.org/fhir/consentcategorycodes changed to<br> http://terminology.hl7.org/CodeSystem/consentcategorycodes, resulting in a different code list</li>
<li>Binding strength changed from example to extensible in R4</li>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.patient<ul>
<li>0..1</li>
<li>Reference (Patient)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.patient<ul>
<li>0..1</li>
<li>Reference (UKCore-Patient)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.patient<ul>
<li>1..1</li>
<li>Reference (CareConnect-Patient-1)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Mimimum cardinality changed from 1 to 0 in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.period<ul>
<li>0..1</li>
<li>Period</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.period is recorded in Consent.provision.period in R4.</li>
</ul>
</td>
</tr>

<!--
<tr>
<td  class="comparison-fhir">Consent.dateTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.dateTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.dateTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td  class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td  class="comparison-fhir">Consent.performer<ul>
<li>0..1</li>
<li>Reference (Organization | Patient | Practitioner | PractitionerRole | RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.performer<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-PractitionerRole | UKCore-RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.consentingParty<ul>
<li>0..1</li>
<li>Reference (CareConnect-Organization-1 | CareConnect-Patient-1 | CareConnect-Practitioner-1 | CareConnect-RelatedPerson-1)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Renamed 'performer' in R4.</li>
<li>Added target reference to PractitionerRole in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.actor<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.actor is recorded in Consent.provision.actor in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.action
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/ValueSet/<br>ConsentActionCodes (example)</li>
</ul>
</td>
<td  class="comparison-v">
<ul>
<li>Consent.action is recorded in Consent.provision.action in R4.</li>
</ul>
</td>
</tr>

<!--
<tr>
<td  class="comparison-fhir">Consent.organization<ul>
<li>0..1</li>
<li>Reference (Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.organization<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.organization<ul>
<li>0..1</li>
<li>Reference (CareConnect-Organization-1)</li>
</ul>
</td>
<td  class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td  class="comparison-fhir">Consent.source[x]<ul>
<li>0..1</li>
<li>Attachment<br>
Reference (Consent | Contract | DocumentReference | QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.source[x]<ul>
<li>0..1</li>
<li>Attachment<br>
Reference (UKCore-Consent | Contract | UKCore-DocumentReference | UKCore-QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.source[x]<ul>
<li>0..1</li>
<li>Attachment<br>
Identifier<br>
Reference (CareConnect-Consent-1 | CareConnect-Contract-1 | DocumentReference | QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Choice of data type Identifier removed in R4.</li>
</ul>
</td>
</tr>
<!--
<tr>
<td  class="comparison-fhir">Consent.policy<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.policy.authority<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy.authority<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy.authority<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td  class="comparison-fhir">Consent.policy.uri<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy.uri<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policy.uri<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td  class="comparison-fhir">Consent.policyRule<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-consent-policy.html">consent-policy</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policyRule<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-consent-policy.html">consent-policy</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">Consent.policyRule<ul>
<li>0..1</li>
<li>uri</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Data type changed to CodeableConcept in R4.</li>
<li>Definition changed to: A reference to the specific base computable regulation or policy.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.securityLabel
<ul>
<li>0..*</li>
<li>Coding</li>
<li>http://hl7.org/fhir/ValueSet/<br>security-labels (extensible)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.securityLabel is recorded in Consent.provision.securityLabel in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.purpose
<ul>
<li>0..*</li>
<li>Coding</li>
<li>http://hl7.org/fhir/ValueSet/<br>v3-PurposeOfUse (extensible)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.purpose is recorded in Consent.provision.purpose in R4.</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.dataPeriod<ul>
<li>0..1</li>
<li>Period</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.dataPeriod is recorded in Consent.provision.dataPeriod in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.data<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.data is recorded in Consent.provision.data in R4.</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Consent.except<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Consent.except has been removed in R4, and its use can be covered by Consent.provision and Consent.provision.provision in R4.</li>
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
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>New element in R4.</li>
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
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>New element in R4, replaces STU3 root elements: period, actor, action, securityLabel, purpose, dataPeriod, data, and except.</li>
</ul>
</td>
</tr>

</tbody>
</table>

