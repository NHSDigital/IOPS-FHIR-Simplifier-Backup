## {{page-title}}

The list below contains the element differences between the UKCore and HL7.

### Base Resource Definitions

View further information about <a href="https://www.hl7.org/fhir/R4/resource.html" Target="_blank">FHIR base resource definitions</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">UK Core Cardinality</th>
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
        <td>In the UK Core the format is the following, with the Extension name in PascalCase:<br/><br/><code>UKCore-<i>[Extension name]</i></code>.</td>
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
        <th width="10%">UK Core Cardinality</th>
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
        <td>In the UK Core the format is the following, with the Extension name in PascalCase:<br/><br/><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-<i>[Extension name]</i></code>(in PascalCase).</td>
    </tr>
    <tr>
        <td>identifier</td>
        <td>0..*</td>
        <td>0..0</td>
        <td>Identifier</td>
        <td>identifier SHALL NOT be used within the UKCore</td>
    </tr>
    <tr>
        <td>version</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This will follow the  <a href="https://semver.org/">Semantic Versioning standard</a> <code><i>&lsqb;major.minor.patch&rsqb;</i></code>.<br>
        Further details about <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/DevelopmentandPublication/UKCoreDevelopmentandReleaseManagement#FHIRAssetsVersioning">internal versioning for UK Core assets</a> are available. </td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format is PascalCase:<br/><br/><code>UKCore<i>[Extension name]</i></code> .</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format in Proper Case:<br/><br/><code>UK Core <i>[Extension name]</i> <code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the UK Core these are defined as: 
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
        <td>Only the date, without time, is populated in the UK  Core.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all UK Core Extensions, where the base URL is <code>https://fhir.hl7.org.uk</code>, this will be <code>HL7 UK</code>.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all UK Core Extensions, where the base URL is <code> https://fhir.hl7.org.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The UK Core mandates the use of this element.</td>
    </tr>
        <tr>
        <td>purpose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The UK Core mandates the use of this element.</td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>A copyright statement relating to the Extension and/or its contents.
        <br/><br/>
        All UK Core Extensions SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    <tr>
      <td>fhirVersion</td>
      <td>0..1</td>
      <td>1..1</td>
      <td>code</td>
      <td>The UK Core mandates the use of this element.</td>
    </tr>
  </tbody>
</table>

<br><br>

### The Extension Root Element

Extensions are optional within the UK Core (minimum cardinality of 0), but certain use cases may mandate their use. Currently, all UK Core extensions are modelled as being optional at the extension root element. Where the use case requires an extension to be mandated, the Implementation Guide for that use case will specify the requirements.

### Extension Bindings When the Value is a Coded type
If any of the <code>extension.value</code> elements is constrained to a coded type e.g. one of Code, Coding, or CodeableConcept, the <code>extension.value</code> SHALL be bound to a ValueSet.

Further information about <a href="https://www.hl7.org/fhir/r4/datatypes.html">FHIR datatypes</a> is available.

### Cardinality of a value[x] element
**Simple extension** - The UK Core mandates the use of <code>Extension.value[x]</code> for a simple extension, that is, a cardinality of 1..1.

**Complex extension** - The UK Core mandates the use of <code>Extension.extension:<i>[Element]</i>.value[x]</code> for a complex extension, that is, a cardinality of 1..1.


---
