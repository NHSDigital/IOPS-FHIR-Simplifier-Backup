# {{page-title}}

<div markdown="span" class="alert alert-info" role="alert"><h4><i class="fa fa-star"></i> Important</h4>
Note: The <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Observation?version=1.7.0">UKCore-Observation</a> profile already exists, and underwent discussion and revision during the Clinical and Technical Assurance sprint 6. It has been included in Clinical and Technicial Assurance sprint 7 for discussion and revision under new use cases.
</div>

<table class="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/R4/observation.html">Base R4 Observation</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence/home/profilesandextensions/profile-ukcore-observation?version=1.7.0">Profile UKCore-Observation</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-Observation.guide.md?version=current">CareConnect-Observation</a></th>
<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<tr>
<td  class="comparison-fhir">Observation.identifier.assigner
<ul>
<li>0..1</li>
<li>Reference (Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">Observation.identifier.assigner
<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization)</li>
</ul>
</td>
<td  class="comparison-fhir">Observation.identifier.assigner
<ul>
<li>0..1</li>
<li>Reference (CareConnect-Organization-1)</li>
</ul>
</td>
<td  class="comparison-note">Change:
<ul>
<li>Reference change to UKCore-profile</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">Observation.basedOn
<ul>
<li>0..*</li>
<li>Reference (CarePlan | DeviceRequest | ImmunizationRecommendation | MedicationRequest | NutritionOrder | ServiceRequest)</li>
</ul>
</td>
<td  class="comparison-fhir">Observation.basedOn
<ul>
<li>0..*</li>
<li>Reference (DeviceRequest | ImmunizationRecommendation | NutritionOrder | UKCore-CarePlan | UKCore-MedicationRequest | UKCore-ServiceRequest)</li>
</ul>
</td>
<td  class="comparison-fhir">Observation.basedOn
<ul>
<li>0..*</li>
<li>Reference (CareConnect-CarePlan-1 | DeviceRequest | ImmunizationRecommendation | NutritionOrder | CareConnect-ReferralRequest-1 | CareConnect-MedicationRequest-1 | CareConnect-ProcedureRequest-1)</li>
</ul>
</td>
<td  class="comparison-note">Target Type Reference changes for R4:
<ul>
<li>Added: ServiceRequest</li>
<li>Removed: ProcedureRequest, ReferralRequest</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.partOf
<ul>
<li>0..*</li>
<li>Reference (MedicationAdministration | MedicationDispense | MedicationStatement | Procedure | Immunization | ImagingStudy)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.partOf
<ul>
<li>0..*</li>
<li>Reference (UKCore-ImagingStudy | UKCore-Immunization | UKCore-MedicationAdministration | UKCore-MedicationDispense | UKCore-MedicationStatement | UKCore-Procedure)</li>
</ul>
</td>
<td>
</td>
<td  class="comparison-note">R4 Changes:
<ul>
<li>Added Element in R4</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.code.coding
<ul>
<li>0..*</li>
<li>LOINC Codes (Example)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.code.coding:snomedCT
<ul>
<li>0..*</li>
<li>UKCoreObservationType (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.code.coding:snomedCT
<ul>
<li>0..1</li>
<li>Care Connect Observation Type (extensible)</li>
</ul>
</td>
<td  class="comparison-note">ValueSet Changes:<ul>
<li>Sliced to carry SNOMED CT (preferred) and LOINC ValueSets in UK Core</li>
</ul></td>
</tr>



<tr>
<td class="comparison-fhir">Observation.status
<ul>
<li>1..1</li>
<li>ObservationStatus (Required)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.status
<ul>
<li>1..1</li>
<li>ObservationStatus (Required)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.status
<ul>
<li>1..1</li>
<li>ObservationStatus (Required)</li>
</ul>
</td>
<td  class="comparison-note">R4 Change:
<ul>
<li>
Changed value set from http://hl7.org/fhir/ValueSet/observation-status to http://hl7.org/fhir/ValueSet/observation-status|4.0.1/</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.subject
<ul>
<li>0..1</li>
<li>Reference (Patient | Group | Device | Location)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.subject
<ul>
<li>0..1</li>
<li>Reference (Group | UKCore-Device | UKCore-Location | UKCore-Patient)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.subject
<ul>
<li>0..1</li>
<li>Reference (Group | Device | CareConnect-Patient-1 | CareConnect-Location-1)</li>
</ul>
</td>
<td  class="comparison-note">Changes:<ul>
<li>Reference changes to UKCore-profile</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.focus
<ul>
<li>0..*</li>
<li>Reference (Any)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.focus
<ul>
<li>0..*</li>
<li>Reference (Resource)</li>
</ul>
</td>
<td class="comparison-fhir"></td>
<td  class="comparison-note">R4 Change:
<ul>
<li>Added Element</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.encounter
<ul>
<li>0..1</li>
<li>Reference (Encounter)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.encounter
<ul>
<li>0..1</li>
<li>Reference (UKCore-Encounter)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.context
<ul>
<li>0..1</li>
<li>Reference (CareConnect-EpisodeOfCare-1 | CareConnect-Encounter-1)</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:
<ul>
<li>Renamed from context to encounter</li>
<li>Type Reference: Removed Target Type EpisodeOfCare</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.effective[x]
<ul>
<li>0..1</li>
<li>effectiveDateTime, effectivePeriod, effectiveTiming,  effectiveInstant</li>
</ul>
</td>
<td class="comparison-fhir">Observation.effective[x]
<ul>
<li>0..1</li>
<li>effectiveDateTime, effectivePeriod, effectiveTiming,  effectiveInstant</li>
</ul>
</td>
<td class="comparison-fhir">Observation.effective[x]
<ul>
<li>0..1</li>
<li>effectiveDateTime, effectivePeriod</li>
</ul>
</td>
<td  class="comparison-note">Added Types for R4:
<ul>
<li>Timing</li>
<li>Instant</li></td>
</tr>
   
<tr>
<td class="comparison-fhir">Observation.performer
<ul>
<li>0..*</li>
<li>Reference (Practitioner | PractitionerRole | Organization | CareTeam | Patient | RelatedPerson)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.performer
<ul>
<li>0..*</li>
<li>Reference (UKCore-CareTeam | UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-PractitionerRole | UKCore-RelatedPerson)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.performer
<ul>
<li>0..*</li>
<li>Reference (CareConnect-RelatedPerson-1 | CareConnect-Patient-1 | CareConnect-Organization-1 | CareConnect-Practitioner-1)</li>
</ul>
</td>
<td  class="comparison-note">Added Target Type References for R4: 
<ul>
<li>PractitionerRole</li>
<li>CareTeam</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.value[x]
<ul>
<li>0..1</li>
<li>Quantity |CodeableConcept |string |boolean |integer |Range |Ratio |SampledData |time |dateTime |Period</li>
</ul>
</td>
<td class="comparison-fhir">Observation.value[x]
<ul>
<li>0..1</li>
<li>Quantity |CodeableConcept |string |boolean |integer |Range |Ratio |SampledData |time |dateTime |Period</li>
</ul>
</td>
<td class="comparison-fhir">Observation.value[x]
<ul>
<li>0..1</li>
<li>Quantity |CodeableConcept |string |boolean |Range |Ratio |SampledData |Attachment |time |dateTime |Period</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:
<ul>
<li>Add Type: Integer</li>
<li>Remove Type: Attachment</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Observation.dataAbsentReason
<ul>
<li>0..1</li>
<li>DataAbsentReason (Extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.dataAbsentReason
<ul>
<li>0..1</li>
<li>DataAbsentReason (Extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.dataAbsentReason
<ul>
<li>0..1</li>
<li>Observation Value Absent Reason (extensible)</li>
</ul>
</td>
<td  class="comparison-note">R4 ValueSet and CodeSystem changes:<ul>
<li>Change value set from http://hl7.org/fhir/ValueSet/observation-valueabsentreason to http://hl7.org/fhir/ValueSet/data-absent-reason</li>
<li>Change code system for extensibly bound codes from "http://hl7.org/fhir/data-absent-reason" to "http://terminology.hl7.org/CodeSystem/data-absent-reason"</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..*</li>
<li>Observation Interpretation Codes (Extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..*</li>
<li>ObservationInterpretationCodes (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..1</li>
<li>Observation Interpretation Codes (extensible)</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Max Cardinality changed from 1 to *</li>
<li>Change code system for extensibly bound codes from "http://terminology.hl7.org/CodeSystem/v2-0078" to "http://terminology.hl7.org/CodeSystem/v3-ObservationInterpretation"</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.note
<ul>
<li>0..*</li>
<li>Annotation</li>
</ul>
</td>
<td class="comparison-fhir">Observation.note
<ul>
<li>0..*</li>
<li>Annotation</li>
</ul>
</td>
<td class="comparison-fhir">Observation.comment
<ul>
<li>0..1</li>
<li>string</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Renamed from comment to note</li>
<li>Max Cardinality changed from 1 to *</li>
<li>Type changed from string to Annotation</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.note.author[x].authorReference
<ul>
<li>0..1</li>
<li>Reference (Practitioner | Patient | RelatedPerson | Organization)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.note.author[x].authorReference
<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-RelatedPerson)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.comment
<ul>
<li>0..1</li>
<li>string</li>
</ul>
</td>
<td  class="comparison-note">Changes:<ul>
<li>References not present in Care Connect</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.bodySite.coding
<ul>
<li>0..*</li>
<li>SNOMED CT Body Structures (Example)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.bodySite.coding:snomedCT
<ul>
<li>0..1</li>
<li>UKCoreBodySite (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.bodySite.coding:snomedCT
<ul>
<li>0..1</li>
<li>Care Connect Body Site (preferred)</li>
</ul>
</td>
<td  class="comparison-note">Changes:<ul>
<li>Sliced in UKCore-to carry SNOMED CT ((preferred) ValueSet</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.method
<ul>
<li>0..1</li>
<li>Observation Methods (Example)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.method
<ul>
<li>0..1</li>
<li>ObservationMethods (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.method
<ul>
<li>0..1</li>
<li>Observation Methods (example)</li>
</ul>
</td>
<td  class="comparison-note">Changes:<ul>
<li>ValueSet binding strength changed to Extensible in the UK Core</li>
</ul></td>
</tr>



<tr>
<td class="comparison-fhir">Observation.specimen
<ul>
<li>0..1</li>
<li>Reference (Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.specimen
<ul>
<li>0..1</li>
<li>Reference (UKCore-Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.specimen
<ul>
<li>0..1</li>
<li>Reference (CareConnect-Specimen-1)</li>
</ul>
</td>
<td  class="comparison-note">Change:<ul>
<li>Reference change to UKCore-profile</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.device
<ul>
<li>0..1</li>
<li>Reference (Device | DeviceMetric)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.device
<ul>
<li>0..1</li>
<li>Reference (DeviceMetric | UKCore-Device)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.device
<ul>
<li>0..1</li>
<li>Reference (Device | DeviceMetric)</li>
</ul>
</td>
<td  class="comparison-note">Change:<ul>
<li>Reference change to UKCore-profile</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.referenceRange.type
<ul>
<li>0..1</li>
<li>Observation Reference Range Meaning Codes (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.referenceRange.type
<ul>
<li>0..1</li>
<li>ObservationReferenceRangeMeaningCodes (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.referenceRange.type
<ul>
<li>0..1</li>
<li>Observation Reference Range Meaning Codes (extensible)</li>
</ul>
</td>
<td  class="comparison-note">R4 Changed Binding Strength:<ul>
<li>From extensible to preferred</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.hasMember
<ul>
<li>0..*</li>
<li>Reference (Observation | QuestionnaireResponse | MolecularSequence)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.hasMember
<ul>
<li>0..*</li>
<li>Reference (MolecularSequence | UKCore-Observation | UKCore-QuestionnaireResponse)</li>
</ul>
</td>
<td class="comparison-fhir">
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Added Element</li>
</ul></td>
</tr>


<tr>
<td class="comparison-fhir">Observation.derivedFrom
<ul>
<li>0..*</li>
<li>Reference (DocumentReference | ImagingStudy | Media | QuestionnaireResponse | Observation | MolecularSequence)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.derivedFrom
<ul>
<li>0..*</li>
<li>Reference (Media | MolecularSequence | UKCore-DocumentReference | UKCore-ImagingStudy | UKCore-Observation | UKCore-QuestionnaireResponse)</li>
</ul>
</td>
<td class="comparison-fhir"></td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Added Element</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.component.code
<ul>
<li>1..1</li>
<li>LOINC Codes (Example)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.code.coding:snomedCT
<li>0..*</li>
<li>UKCoreObservationType ((preferred))</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.code.coding:snomedCT
<li>0..1</li>
<li>Care Connect Observation Type (preferred)</li>
</ul>
</td>
<td  class="comparison-note">Changes:<ul>
<li>Sliced in UKCore-to carry SNOMED CT (preferred) ValueSet</li>
</ul></td>
</tr>


<tr>
<td class="comparison-fhir">Observation.component.value[x]
<ul>
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range| Ratio | SampledData  |time | dateTime |Period</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.value[x]
<ul>
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range| Ratio | SampledData  |time | dateTime |Period</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.value[x]
<li>0..1</li>
<li>Quantity | CodeableConcept | string | Range| Ratio | SampledData  | Attachment | time | dateTime | Period</li>
</ul>
</td>
<td  class="comparison-note">R4 Type changes:<ul>
<li>Added: boolean</li>
<li>Added: integer</li>
<li>Removed: Attachment</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.component.dataAbsentReason
<ul>
<li>0..1</li>
<li>DataAbsentReason (Extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.dataAbsentReason
<ul>
<li>0..1</li>
<li>DataAbsentReason (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.dataAbsentReason
<ul>
<li>0..1</li>
<li>Observation Value Absent Reason (extensible)</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Change value set from http://hl7.org/fhir/ValueSet/observation-valueabsentreason to http://hl7.org/fhir/ValueSet/data-absent-reason</li>
<li>Change code system for extensibly bound codes from "http://hl7.org/fhir/data-absent-reason" to "http://terminology.hl7.org/CodeSystem/data-absent-reason"</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..*</li>
<li>Observation Interpretation Codes (Extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..*</li>
<li>ObservationInterpretationCodes (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Observation.interpretation
<ul>
<li>0..1</li>
<li>Observation Interpretation Codes (extensible)</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Max Cardinality changed from 1 to *</li>
<li>Change code system for extensibly bound codes from "http://terminology.hl7.org/CodeSystem/v2-0078" to "http://terminology.hl7.org/CodeSystem/v3-ObservationInterpretation"</li>
</ul></td>
</tr>

<tr>
<td class="comparison-fhir">
</td>
<td class="comparison-fhir">
</td>
<td class="comparison-fhir">Observation.related
<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">R4 Changes:<ul>
<li>Deleted element</li>
</ul></td>
</tr>

</tbody>
</table>