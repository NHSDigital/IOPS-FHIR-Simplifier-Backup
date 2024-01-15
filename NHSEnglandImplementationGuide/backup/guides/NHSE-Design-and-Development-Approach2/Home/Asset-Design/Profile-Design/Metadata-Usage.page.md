## {{page-title}}

The list below contains the element differences between the HL7 FHIR R4  and NHS England IG. 

### Base Resource Definitions

View further information about <a href="https://www.hl7.org/fhir/R4/resource.html" Target="_blank">FHIR base resource definitions</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
         <td>In the NHS England IG the format is the following, with the FHIRAssetName and Specialism in PascalCase:<br/><br/><code>England-[FHIRAssetName]</i></code>.</td>
    </tr>
    </tbody>
</table>

### StructureDefinition Content

View further information about <a href="https://www.hl7.org/fhir/R4/structuredefinition.html" Target="_blank">FHIR Resource StructureDefinition - Content</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>url</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>uri</td>
        <td>In the NHS England IG the format is the following, with the FHIRAssetName and Specialism in PascalCase:<br/><br/><code>https://fhir.nhs.uk/England/StructureDefinition/England-[FHIRAssetName]</i></code>.</td>
    </tr>
    <tr>
        <td>identifier</td>
        <td>0..*</td>
        <td>0..0</td>
        <td>Identifier</td>
        <td>identifier SHALL NOT be used within the NHS England IG</td>
    </tr>
    <tr>
        <td>version</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This will follow the  <a href="https://semver.org/" Target="_blank">Semantic Versioning standard</a> <code>[major.minor.patch]</i></code>.<br>
        Further details about <a href="https://simplifier.net/guide/nhs-england-design-and-development-approach/home/management/version-management/package-versioning.page.md?version=current" Target="_blank">internal versioning for NHS England assets</a> are available. </td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the NHS England IG the format is PascalCase:<br/><br/><code>England[FHIRAssetName]</i></code> .</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the NHS England IG the format is Proper Case:<br/><br/><code>England [FHIRAssetName]</i><code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England IG these are defined as: 
        <ul>
        <li><samp>draft</samp> - Profiles in development</li>
        <li><samp>active</samp> - Profiles that have been approved via Clinical and Technical Assurance</li>
        <li><samp>retired</samp> - Profiles that are no longer required</li>
        </ul></td>
    </tr>
    <tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in NHS England.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all NHS England Profiles, where the base URL is <code>https://fhir.nhs.uk/England</code>, the name of the publisher will be NHS England.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>See {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all NHS England Profiles, where the base URL is <code> https://fhir.nhs.uk/England</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The NHS England IG mandates the use of this element.</td>
    </tr>
        <tr>
        <td>purpose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>This provides traceability of ''why'' the resource is either needed or ''why'' it is defined as it is.</td>
        </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td> All NHS England Profiles SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    <tr>
        <td>fhirVersion</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>The NHS England IG mandates the use of this element.</td>
    </tr>
    <tr>
        <td>snapshot</td>
        <td>0..1</td>
        <td>0..0</td>
        <td>BackboneElement</td>
        <td>Snapshots SHALL NOT be used within the NHS England IG</td>
    </tr>
    <tr>
        <td>differential<br>.element<br>.defaultValue[x]</td>
        <td>0..1</td>
        <td>0..0</td>
        <td>*</td>
        <td>Defining default values creates many difficulties in implementation (e.g. when is a value missing?). For these reasons, default values SHALL NOT be used within the NHS England IG.</td>
  </tr>
  </tbody>
</table>

<br><br>

---
