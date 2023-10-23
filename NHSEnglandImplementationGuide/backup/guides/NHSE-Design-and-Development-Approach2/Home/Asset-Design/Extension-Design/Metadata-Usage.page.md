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
        <td>In the NHS England the format is the following, with the Extension name in PascalCase:<br/><br/><code>Extension-England-[Name]</code>.</td>
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
        <td>In NHS England the format is the following, with the Extension name in PascalCase:<br/><br/><code>https://fhir.nhs.uk/England/StructureDefinition/Extension-England-[Name]</i></code>.</td>
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
        <td>This will follow the  <a href="https://semver.org/">Semantic Versioning standard</a> <code>&lsqb;major.minor.patch&rsqb;</code>.<br>
        Further details about <a href="https://simplifier.net/guide/nhs-england-design-and-development-approach/home/management/version-management/package-versioning.page.md?version=current" Target="_blank">internal versioning for NHS England assets</a> are available. </td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In NHS England the format is PascalCase:<br/><br/><code> ExtensionEngland[Name]</code>.</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the NHS England the format in Proper Case:<br/><br/><code>Extension England [Name]</i><code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England these are defined as: 
        <ul>
        <li>draft - Extensions in development</li>
        <li>active - Extensions that have been approved via Clinical and Technical Assurance</li>
        <li>retired - Extensions that are no longer required</li>
        </ul></td>
    </tr>
    <tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in the NHS England.</td>
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
        <td>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all NHS England Extensions, where the base URL is <code> https://fhir.nhs.uk/England</code>.</td>
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
  </tbody>
</table>

<br><br>

### The Extension Root Element

Extensions are optional within the NHS England (minimum cardinality of 0), but certain use cases may mandate their use. Currently, all NHS England extensions are modelled as being optional at the extension root element. Where the use case requires an extension to be mandated, the Implementation Guide for that use case will specify the requirements. If it has been agreed that it is mandated for ALL NHS England use cases there the NHS England profile will mandated the extension.

### Extension Bindings When the Value is a Coded type
If any of the <code>extension.value</code> elements is constrained to a coded type e.g. one of Code, Coding, or CodeableConcept, the <code>extension.value</code> SHALL be bound to a ValueSet.

Further information about <a href="https://www.hl7.org/fhir/r4/datatypes.html">FHIR datatypes</a> is available.

### Cardinality of a value[x] element
**Simple extension** - The NHS England IG mandates the use of <code>Extension.value[x]</code> for a simple extension, that is, a cardinality of 1..1.

**Complex extension** - The NHS England IG mandates the use of <code>Extension.extension:[Element].value[x]</code> for a complex extension, that is, a cardinality of 1..1.

---
