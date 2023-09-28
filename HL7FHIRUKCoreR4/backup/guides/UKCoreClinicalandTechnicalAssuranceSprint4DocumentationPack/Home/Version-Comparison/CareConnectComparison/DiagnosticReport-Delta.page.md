# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/R4/DiagnosticReport.html">Base R4 DiagnosticReport</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-DiagnosticReport?version=1.6.0">Profile UKCore-DiagnosticReport</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-DiagnosticReport.guide.md?version=current">CareConnect-DiagnosticReport-1</a></th>
<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<tr>
<td class="comparison-fhir">DiagnosticReport.basedOn
<ul>
<li>0..*</li>
<li>Reference</li>
<li>Reference (CarePlan | ImmunizationRecommendation | MedicationRequest | NutritionOrder | ServiceRequest)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.basedOn
<ul>
<li>0..*</li>
<li>Reference</li>
<li>Reference (UKCore-CarePlan | ImmunizationRecommendation | UKCore-MedicationRequest | NutritionOrder | UKCore-ServiceRequest)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.basedOn
<ul>
<li>0..*</li>
<li>Reference</li>
<li>Reference (CareConnect-CarePlan-1 | CareConnect-MedicationRequest-1 | CareConnect-ProcedureRequest-1 | CareConnect-ReferralRequest-1)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Reference type changed from ProcedureRequest and ReferralRequest, to ServiceRequest in R4.</li>
<li>Reference types for ImmunizationRecommendation and NutritionOrder were removed in CareConnect STU3.</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-diagnostic-report-status.html">diagnostic-report-status</a> (required)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-diagnostic-report-status.html">diagnostic-report-status</a> (required)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.status
<ul>
<li>1..1</li>
<li>code</li>
<li>http://hl7.org/fhir/ValueSet/<br>diagnostic-report-status (required)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Change value set from <br> http://hl7.org/fhir/ValueSet/diagnostic-report-status<br>to<br> http://hl7.org/fhir/ValueSet/diagnostic-report-status|4.0.1</li>
</ul>
</td>
</tr>


<tr>
<td class="comparison-fhir">DiagnosticReport.category
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-diagnostic-service-sections.html">diagnostic-service-sections</a> (example)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.category
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-diagnostic-service-sections.html">diagnostic-service-sections</a> (example)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.category
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/ValueSet/<br>diagnostic-service-sections (preferred)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Maximum cardinality changed from 1 to * in R4.</li>
<li>Change value set from<br> http://hl7.org/fhir/ValueSet/diagnostic-service-sections<br>to<br> http://hl7.org/fhir/ValueSet/diagnostic-service-sections|4.0.1</li>
<li>Binding strength changed from preferred to example in R4</li>
</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.code
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://hl7.org/fhir/R4/valueset-report-codes.html">report-codes</a> (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.code
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://simplifier.net/hl7fhirukcorer4/ukcore-reportcodesnct">UKCore-ReportSnCT</a> (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.code
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/ValueSet/<br>report-codes (preferred)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Change value set from http://hl7.org/fhir/ValueSet/report-codes to http://hl7.org/fhir/ValueSet/report-codes|4.0.1</li>
</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.subject<ul>
<li>0..1</li>
<li>Reference (Device | Group | Location | Patient)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.subject<ul>
<li>0..1</li>
<li>Reference (UKCore-Device | Group | UKCore-Location | UKCore-Patient)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.subject<ul>
<li>1..1</li>
<li>Reference (Device | Group | CareConnect-Location-1 | CareConnect-Patient-1)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Minimum cardinality changed from 1 to 0 in R4.</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.encounter<ul>
<li>0..1</li>
<li>Reference (Encounter)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.encounter<ul>
<li>0..1</li>
<li>Reference (UKCore-Encounter)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.context<ul>
<li>0..1</li>
<li>Reference (CareConnect-Encounter-1)</li>
</ul>
</td>
<td class="comparison-note"><ul>
<li>Renamed 'encounter' in R4.</li>
</ul></td>
</tr>

<!--
<tr>
<td class="comparison-fhir">DiagnosticReport.effective[x]<ul>
<li>0..1</li>
<li>dateTime<br>
Period</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.effective[x]<ul>
<li>0..1</li>
<li>dateTime<br>
Period</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.effective[x]<ul>
<li>0..1</li>
<li>dateTime<br>
Period</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.issued<ul>
<li>0..1</li>
<li>instant</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.issued<ul>
<li>0..1</li>
<li>instant</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.issued<ul>
<li>0..1</li>
<li>instant</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">DiagnosticReport.performer<ul>
<li>0..*</li>
<li>Reference (CareTeam | Organization | Practitioner | PractitionerRole)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.performer<ul>
<li>0..*</li>
<li>Reference (UKCore-CareTeam | UKCore-Organization | UKCore-Practitioner | UKCore-PractitionerRole)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.performer<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Type changed from BackboneElement to Reference in R4.</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.resultsInterpreter<ul>
<li>0..*</li>
<li>Reference (CareTeam | Organization | Practitioner | PractitionerRole)</li>
</ul>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.resultsInterpreter<ul>
<li>0..*</li>
<li>Reference (UKCore-CareTeam | UKCore-Organization | UKCore-Practitioner | UKCore-PractitionerRole)</li>
</ul>
</ul>
</td>
<td class="comparison-fhir">&nbsp;</td>
<td class="comparison-note">
<ul>
<li>New element in R4.</li>
</ul>
</td>
</tr>

<!--
<tr>
<td class="comparison-fhir">DiagnosticReport.specimen<ul>
<li>0..*</li>
<li>Reference (Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.specimen<ul>
<li>0..*</li>
<li>Reference (UKCore-Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.specimen<ul>
<li>0..*</li>
<li>Reference (CareConnect-Specimen-1)</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.result<ul>
<li>0..*</li>
<li>Reference (Observation)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.result<ul>
<li>0..*</li>
<li>Reference (UKCore-Observation)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.result<ul>
<li>0..*</li>
<li>Reference (CareConnect-Observation-1)</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">DiagnosticReport.imagingStudy<ul>
<li>0..*</li>
<li>Reference (ImagingStudy)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.imagingStudy<ul>
<li>0..*</li>
<li>Reference (UKCore-ImagingStudy)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.imagingStudy<ul>
<li>0..*</li>
<li>Reference (ImagingStudy | ImagingManifest)</li>
</ul>
</td>
<td class="comparison-note"><ul>
<li>Reference to type ImagingManifest removed in R4.</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">DiagnosticReport.media<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.media<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.image<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-note"><ul>
<li>Renamed 'media' in R4.</li>
</ul></td>
</tr>

<!--
<tr>
<td class="comparison-fhir">DiagnosticReport.conclusion<ul>
<li>0..1</li>
<li>string</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.conclusion<ul>
<li>0..1</li>
<li>string</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.conclusion<ul>
<li>0..1</li>
<li>string</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">DiagnosticReport.conclusionCode
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-clinical-findings.html">clinical-findings</a> (example)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.conclusionCode
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://simplifier.net/hl7fhirukcorer4/ukcore-findingcode">UKCore-FindingCode</a> (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.codedDiagnosis
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>https://fhir.hl7.org.uk/STU3/ValueSet<br>CareConnect-FindingCode-1 (preferred)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Renamed 'conclusionCode' in R4.</li>
</td>
</tr>

<!--
<tr>
<td class="comparison-fhir">DiagnosticReport.presentedFrom<ul>
<li>0..*</li>
<li>Attachment</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.presentedFrom<ul>
<li>0..*</li>
<li>Attachment</li>
</ul>
</td>
<td class="comparison-fhir">DiagnosticReport.presentedFrom<ul>
<li>0..*</li>
<li>Attachment</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

</tbody>
</table>

