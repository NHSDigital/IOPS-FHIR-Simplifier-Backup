# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Specimen?version=1.6.0">Profile UKCore-Specimen</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/Specimen.html">R5 Snapshot Specimen</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">


<tr>
<td class="comparison-fhir">Specimen.subject<ul>
<li>0..1</li>
<li>Reference (UKCore-Device | Group | UKCore-Location | UKCore-Patient)</li>
</ul></td>
<td class="comparison-fhir">Specimen.subject<ul>
<li>0..1</li>
<li>Reference (BiologicallyDerivedProduct | Device | Group | Location | Patient)</li>
</ul>
</td>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Added reference to BiologicallyDerivedProduct</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Specimen.combined<ul>
<li>0..1</li>
<li>code</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-specimen-combined.html">specimen-combined</a> (required)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Specimen.role<ul>
<li>0..*</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-specimen-role.html">specimen-role</a> (preferred)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Specimen.feature<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td class="comparison-fhir">Specimen.collection.collector<ul>
<li>0..1</li>
<li>Reference (UKCore-Practitioner | UKCore-PractitionerRole)</li>
</ul>
</td>
<td class="comparison-fhir">Specimen.collection.collector<ul>
<li>0..1</li>
<li>Reference (Patient | Practitioner | PractitionerRole | RelatedPerson)</li>
</ul>
</td>
<td class="comparison-note">
<ul>
<li>Added reference to Patient and RelatedPerson</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Specimen.collection.device<ul>
<li>0..1</li>
<li>CodeableReference (Device)</li>
<li>SpecimenCollectionDevice (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">Specimen.collection.procedure<ul>
<li>0..1</li>
<li>Reference (Procedure)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">Specimen.collection.bodySite<ul>
<li>0..1</li>
<li>CodeableConcept</li>
<li>http://hl7.org/fhir/r4/valueset<br><a href="https://hl7.org/fhir/r4/valueset-body-site.html">body-site</a> (example)</li>
</ul></td>
<td  class="comparison-fhir">Specimen.collection.bodySite<ul>
<li>0..1</li>
<li>CodeableReference (BodyStructure)</li>
<li>http://hl7.org/fhir/valueset<br><a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-body-site.html">body-site</a> (example)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Change from CodeableConcept to CodeableReference</li>
</tr>

<tr>
<td  class="comparison-fhir">Specimen.processing<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Specimen.processing<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li><b>Removed sub elements in R5:</b> </li>
<li>Specimen.processing.procedure</li>
<li><b>New sub elements in R5:</b> </li>
<li>Specimen.processing.method, 0..1, <a href="https://hl7.org/fhir/5.0.0-snapshot3/valueset-specimen-processing-method.html">specimen-processing-method</a> (example)</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">Specimen.container<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-fhir">Specimen.container<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li><b>Removed sub elements in R5:</b> </li>
<li>Specimen.container.identifier</li>
<li>Specimen.container.description</li>
<li>Specimen.container.type</li>
<li>Specimen.container.capacity</li>
<li>Specimen.container.additive[x]</li>
<li><b>New sub elements in R5:</b> </li>
<li>Specimen.container.device, 1..1, Reference (Device)</li>
<li>Specimen.container.location, 0..1, Reference (Location)</li>
</ul>
</td>
</tr>


</tbody>
</table>

