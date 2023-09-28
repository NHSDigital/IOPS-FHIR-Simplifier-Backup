# {{page-title}}

<table id="assets">
<thead>
<tr>
<th class="comparison-fhir"><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-DiagnosticReport?version=1.6.0">Profile UKCore-DiagnosticReport</a></th>
<th class="comparison-fhir"><a href="https://hl7.org/fhir/5.0.0-snapshot3/DiagnosticReport.html">R5 Snapshot DiagnosticReport</a></th>

<th class="comparison-note">Notes</th>
</tr>
</thead>
<tbody style="vertical-align:top">



<tr>
<td  class="comparison-fhir">DiagnosticReport.subject
<ul>
<li>0..1</li>
<li>Reference (UKCore-Device | Group | UKCore-Location | UKCore-Patient)</li>
</ul></td>
<td  class="comparison-fhir">DiagnosticReport.subject
<ul>
<li>0..1</li>
<li>Reference (BiologicallyDerivedProduct | Device | Group | Location | Medication | Organization | Patient | Procedure | Practitioner | Substance)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Added references to: Organization, Procedure, Practitioner, Medication, Substance, BiologicallyDerivedProduct</li>
</ul>
</td>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">DiagnosticReport.note<ul>
<li>0..*</li>
<li>Annotation</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">DiagnosticReport.study<ul>
<li>0..*</li>
<li>Reference (GenomicStudy | ImagingStudy)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">DiagnosticReport.supportingInfo<ul>
<li>0..*</li>
<li>BackboneElement</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">DiagnosticReport.media.link<ul>
<li>1..1</li>
<li>Reference (Media)</li>
</ul>
<td  class="comparison-fhir">DiagnosticReport.media.link<ul>
<li>1..1</li>
<li>Reference (DocumentReference)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>Reference swapped from Media to DocumentReference</li>
</tr>


<tr>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-fhir">DiagnosticReport.composition<ul>
<li>0..1</li>
<li>Reference (Composition)</li>
</ul>
</td>
<td  class="comparison-note">
<ul>
<li>New element added in R5</li>
</tr>

<tr>
<td  class="comparison-fhir">DiagnosticReport.imagingStudy<ul>
<li>0..1</li>
<li>Reference (UKCore-ImagingStudy)</li>
</ul>
</td>
<td  class="comparison-fhir">&nbsp;</td>
<td  class="comparison-note">
<ul>
<li>Element removed in R5</li>
<li>Replaced by DiagnosticReport.study</li>
</ul>
</td>
</tr>

</tbody>
</table>

