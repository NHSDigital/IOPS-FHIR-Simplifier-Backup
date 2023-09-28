# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/R4/Specimen.html">Base R4 Specimen</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Specimen?version=1.6.0">Profile UKCore-Specimen</a></th>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/hl7fhircareconnectprofilesstu3/Home/ProfilesandExtensions/AllAssets/AllProfiles/ProfileCareConnect-Specimen.guide.md?version=current">CareConnect-Specimen-1</a></th>
<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">

<!--
<tr>
<td class="comparison-fhir">Specimen.accessionIdentifier
<ul>
<li>0..1</li>
<li>Identifier</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.accessionIdentifier
<ul>
<li>0..1</li>
<li>Identifier</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.accessionIdentifier
<ul>
<li>0..1</li>
<li>Identifier</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">Specimen.status
<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-specimen-status.html">specimen-status</a> (required)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.status
<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-specimen-status.html">specimen-status</a> (required)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.status
<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/ValueSet/<br>specimen-status (required)</li>
</ul>
</td>
<td class="comparison-note"><ul>
<li>Change value set from <br>http://hl7.org/fhir/ValueSet/specimen-status<br>to<br> http://hl7.org/fhir/ValueSet/specimen-status|4.0.1
</td>
</tr>

<!--
<tr>
<td class="comparison-fhir">Specimen.type
<ul>
<li>0..1</li>
<li>code</li>
<li>http://terminology.hl7.org/ValueSet/v2-0487 (example)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.type
<ul>
<li>0..1</li>
<li>code</li>
<li>http://terminology.hl7.org/ValueSet/v2-0487 (example)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.type
<ul>
<li>0..1</li>
<li>code</li>
<li>http://terminology.hl7.org/ValueSet/v2-0487 (example)</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->


<tr>
<td class="comparison-fhir">Specimen.subject<ul>
<li>0..1</li>
<li>Reference (Device | Group | Location | Patient)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.subject<ul>
<li>0..1</li>
<li>Reference (UKCore-Device | Group | UKCore-Location | UKCore-Patient)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.subject<ul>
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

<!--
<tr>
<td class="comparison-fhir">Specimen.receivedTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.receivedTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.receivedTime<ul>
<li>0..1</li>
<li>dateTime</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.parent<ul>
<li>0..*</li>
<li>Reference (Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.parent<ul>
<li>0..*</li>
<li>Reference (UKCore-Specimen)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.parent<ul>
<li>0..*</li>
<li>Reference (CareConnect-Specimen-1)</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">Specimen.request<ul>
<li>0..*</li>
<li>Reference (ServiceRequest)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.request<ul>
<li>0..*</li>
<li>Reference (UKCore-ServiceRequest)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.request<ul>
<li>0..*</li>
<li>Reference (CareConnect-ProcedureRequest-1)</li>
</ul>
</td>
<td class="comparison-note">Reference to type ProcedureRequest in STU3, replaced with ServiceRequest in R4</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection<ul>
<li>0..1</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">&nbsp;</td>
<td class="comparison-fhir">&nbsp;</td>
<td class="comparison-fhir">Specimen.collection.extension:fastingStatus
<ul>
<li>0..1</li>
<li>CodeableConcept<br>Duration</li>
<li>http://terminology.hl7.org/ValueSet/v2-0916 (extensible)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>CareConnect Extension 'fastingStatus' replaced with element 'fastingStatus[x]' in R4.</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection.collector<ul>
<li>0..1</li>
<li>Reference (Practitioner | PractitionerRole)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.collector<ul>
<li>0..1</li>
<li>Reference (UKCore-Practitioner | UKCore-PractitionerRole)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.collector<ul>
<li>0..1</li>
<li>Reference (CareConnect-Practitioner-1)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Added reference to PractitionerRole in R4</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection.duration<ul>
<li>0..1</li>
<li>Duration</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.duration<ul>
<li>0..1</li>
<li>Duration</li>
</ul>
</td>
<td class="comparison-fhir">&nbsp;</td>
<td class="comparison-note">
<ul>
<li>New element in R4</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection.bodySite
<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://hl7.org/fhir/R4/valueset-body-site.html">body-site</a> (example)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.bodySite
<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/R4/valueset<br><a href="https://simplifier.net/hl7fhirukcorer4/ukcore-specimenbodysite">UKCore-SpecimenBodySite</a> (preferred)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.bodySite
<ul>
<li>0..1</li>
<li>code</li>
<li>https://fhir.hl7.org.uk/STU3/ValueSet/<br>areConnect-SpecimenBodySite-1 (extensible)</li>
</ul>
</td>
<td class="comparison-note">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection.fastingStatus[x]
<ul>
<li>0..1</li>
<li>CodeableConcept<br>Duration</li>
<li>http://terminology.hl7.org/ValueSet/v2-0916 (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.fastingStatus[x]
<ul>
<li>0..1</li>
<li>CodeableConcept<br>Duration</li>
<li>http://terminology.hl7.org/ValueSet/v2-0916 (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">
</td>
<td class="comparison-note">
<ul>
<li>New element in R4</li>
</ul>
</td>
</tr>

<!--
<tr>
<td class="comparison-fhir">Specimen.processing<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.processing<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.processing<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">&nbsp;</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.container<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.container<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.container<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td class="comparison-fhir">&nbsp;</td>
</tr>
-->

<tr>
<td class="comparison-fhir">Specimen.condition
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://terminology.hl7.org/ValueSet/v2-0493 (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.condition
<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://terminology.hl7.org/ValueSet/v2-0493 (extensible)</li>
</ul>
</td>
<td class="comparison-fhir">
</td>
<td class="comparison-fhir">
<ul>
<li>New element in R4</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.note<ul>
<li>0..*</li>
<li>Annotation</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.note<ul>
<li>0..*</li>
<li>Annotation</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.note<ul>
<li>0..1</li>
<li>Annotation</li>
</ul>
</td>
<td class="comparison-fhir">
<ul>
<li>Maximum cardinality changed from 1 to * in R4.</li>
</ul>
</td>
</tr>

<tr>
<td class="comparison-fhir">Specimen.note.author[x]<ul>
<li>0..1</li>
<li>Reference (Organization | Patient | Practitioner | RelatedPerson)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.note.author[x]<ul>
<li>0..1</li>
<li>Reference (UKCore-Organization | UKCore-Patient | UKCore-Practitioner | UKCore-RelatedPerson)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.note.author[x]<ul>
<li>0..1</li>
<li>Reference (CareConnect-Patient-1 | CareConnect-Practitioner-1)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Added reference to Organization and RelatedPerson in R4</li>
</ul>
</td>
</tr>

</tbody>
</table>

