# {{page-title}}

<div markdown="span" class="alert alert-info" role="alert"><h4><i class="fa fa-star"></i> Important</h4>
Note: The <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Observation?version=1.7.0">UKCore-Observation</a> profile already exists, and underwent discussion and revision during the Clinical and Technical Assurance sprint 6. It has been included in Clinical and Technicial Assurance sprint 7 for discussion and revision under new use cases.
</div>

<table class="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Observation?version=1.7.0">Profile UKCore-Observation</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/Observation.html">R5 Snapshot Observation</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Observation.instantiates[x]<ul>
<li>0..1</li>
<li>canonical (ObservationDefinition)</li>
<li>Reference (ObservationDefinition)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Observation.triggeredBy<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">Observation.partOf
<ul>
<li>0..*</li>
<li>Reference (UKCore-ImagingStudy | UKCore-Immunization | UKCore-MedicationAdministration | UKCore-MedicationDispense | UKCore-MedicationStatement | UKCore-Procedure)</li>
</ul></td>
<td  class="comparison-fhir">Observation.partOf
<ul>
<li>0..*</li>
<li>Reference (GenomicStudy | ImagingStudy | Immunization | MedicationAdministration | MedicationDispense | MedicationUsage | Procedure)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Removed reference to: MedicationStatement</li>
<li>Added references to: GenomicStudy, MedicationUsage</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Observation.subject
<ul>
<li>0..1</li>
<li>Reference (UKCore-Device | Group | UKCore-Location | UKCore-Patient)</li>
</ul></td>
<td  class="comparison-fhir">Observation.subject
<ul>
<li>0..1</li>
<li>Reference (BiologicallyDerivedProduct | Device | Group | Location | Medication | NutritionProduct | Organization | Patient | Practitioner | Procedure | Substance)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added references to: Organization, Procedure, Practitioner, Medication, Substance, BiologicallyDerivedProduct, NutritionProduct</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Observation.value[x]
<ul>
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range | Ratio | SampledData | time | dateTime | Period</li>
</ul></td>
<td  class="comparison-fhir">Observation.value[x]
<ul>
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range | Ratio | SampledData | time | dateTime | Period | Attachment</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added type Attachment</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Observation.bodyStructure<ul>
<li>0..1</li>
<li>Reference (BodyStructure)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>


<tr>
<td  class="comparison-fhir">Observation.specimen<ul>
<li>0..1</li>
<li>Reference (Specimen)</li>
</ul>
</td>
<td  class="comparison-fhir">Observation.specimen<ul>
<li>0..1</li>
<li>Reference (Specimen | Group)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added reference to Group</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Observation.referenceRange.normalValue<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-observation-referencerange-normalvalue.html">observation-referencerange-normalvalue</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td class="comparison-fhir">Observation.derivedFrom
<ul>
<li>0..*</li>
<li>Reference (UKCore-DocumentReference | UKCore-ImagingStudy | Media | MolecularSequence | UKCore-Observation | UKCore-QuestionnaireResponse)</ul>
</td>
<td class="comparison-fhir">Observation.derivedFrom
<ul>
<li>0..*</li>
<li>Reference (DocumentReference | GenomicStudy | ImagingSelection | ImagingStudy | MolecularSequence | Observation | QuestionnaireResponse)</li>
</ul>
</td>
<td  class="comparison-note"><ul>
<li>Removed reference to Media</li>
<li>Added references to GenomicStudy, ImagingSelection</li>
</ul></td>
</tr>


<tr>
<td class="comparison-fhir">Observation.component.value[x]
<ul>
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range | Ratio | SampledData | time | dateTime | Period</li>
</ul>
</td>
<td class="comparison-fhir">Observation.component.value[x]
<li>0..1</li>
<li>Quantity | CodeableConcept | string | boolean | integer | Range | Ratio | SampledData | time | dateTime | Period | Attachment</li>
</ul>
</td>
<td  class="comparison-note"><ul>
<li>Added type Attachment</li>
</ul></td>
</tr>



</tbody>
</table>

