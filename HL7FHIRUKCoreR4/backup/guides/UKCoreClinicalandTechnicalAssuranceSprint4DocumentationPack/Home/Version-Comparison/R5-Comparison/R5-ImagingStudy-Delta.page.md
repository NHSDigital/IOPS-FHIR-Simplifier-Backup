# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-ImagingStudy?version=1.6.0">Profile UKCore-ImagingStudy</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/ImagingStudy.html">R5 Snapshot ImagingStudy</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<tr>
<td  class="comparison-fhir">ImagingStudy.modality
<ul>
<li>0..*</li>
<li>Coding</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://dicom.nema.org/medical/dicom/current/output/chtml/part16/sect_CID_29.html">CID 29 Acquisition Modality</a> (extensible)</li>
</ul></td>
</td>
<td  class="comparison-fhir">ImagingStudy.modality
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://dicom.nema.org/medical/dicom/current/output/chtml/part16/sect_CID_33.html">CID 33 Modality</a> (extensible)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>Change from Coding to CodeableConcept</li>
<li>Change of ValueSet</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ImagingStudy.series.modality
<ul>
<li>1..1</li>
<li>Coding</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://dicom.nema.org/medical/dicom/current/output/chtml/part16/sect_CID_29.html">CID 29 Acquisition Modality</a> (extensible)</li>
</ul></td>
</td>
<td  class="comparison-fhir">ImagingStudy.series.modality
<ul>
<li>1..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://dicom.nema.org/medical/dicom/current/output/chtml/part16/sect_CID_33.html">CID 33 Modality</a> (extensible)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>Change from Coding to CodeableConcept</li>
<li>Change of ValueSet</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">ImagingStudy.series.bodySite
<ul>
<li>0..1</li>
<li>Coding</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-body-site.html">body-site</a> (example)</li>
</ul></td>
</td>
<td  class="comparison-fhir">ImagingStudy.series.bodySite
<ul>
<li>0..1</li>
<li>CodeableReference</li>
<li>Reference (BodyStructure)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-body-site.html">body-site</a> (example)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>Change from Coding to CodeableReference</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ImagingStudy.series.laterality
<ul>
<li>0..1</li>
<li>Coding</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-bodysite-laterality.html">bodysite-laterality</a> (example)</li>
</ul></td>
</td>
<td  class="comparison-fhir">ImagingStudy.series.laterality
<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://dicom.nema.org/medical/dicom/current/output/chtml/part16/sect_CID_33.html">CID 244 Laterality</a> (example)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>Change from Coding to CodeableConcept</li>
<li>Change of ValueSet</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">ImagingStudy.series.performer.actor<ul>
<li>0..1</li>
<li>Reference (UKCore-CareTeam | UKCore-Device | UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-PractitionerRole | UKCore-RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-fhir">ImagingStudy.series.performer.actor<ul>
<li>0..1</li>
<li>Reference (CareTeam | Device | HealthcareService | Organization | Patient | Practitioner | PractitionerRole | RelatedPerson)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added reference to HealthcareService</li>
</ul>
</td>
</tr>




<tr>
<td  class="comparison-fhir">ImagingStudy.procedureReference<ul>
<li>0..*</li>
<li>Reference (UKCore-Procedure)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ImagingStudy.procedure</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">ImagingStudy.procedureCode<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="http://www.rsna.org/RadLex_Playbook.aspx">http://www.rsna.org/RadLex_Playbook.aspx</a> (extensible)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ImagingStudy.procedure</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ImagingStudy.procedure
<ul>
<li>0..*</li>
<li>CodeableReference (Procedure)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://fhir.loinc.org/ValueSet/loinc-rsna-radiology-playbook/">https://fhir.loinc.org/ValueSet/loinc-rsna-radiology-playbook/</a> (preferred)</li>
</ul></td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ImagingStudy.reasonCode<ul>
<li>0..*</li>
<li>CodeableConcept</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ImagingStudy.reason</li>
</ul>
</td>
</tr>


<tr>
<td  class="comparison-fhir">ImagingStudy.reasonReference<ul>
<li>0..*</li>
<li>Reference (UKCore-Condition | UKCore-DiagnosticReport | UKCore-DocumentReference | UKCore-Observation)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by ImagingStudy.reason</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">ImagingStudy.reason<ul>
<li>0..*</li>
<li>CodeableReference (Condition | DiagnosticReport | DocumentReference | Observation)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-procedure-reason.html">procedure-reason</a> (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

</tbody>
</table>

