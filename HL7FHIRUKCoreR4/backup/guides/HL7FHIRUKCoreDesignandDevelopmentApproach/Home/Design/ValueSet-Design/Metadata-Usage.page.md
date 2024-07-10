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
        <td>In the UK Core the format is the following, with the BusinessName in PascalCase:<br/><br/><code>UKCore-<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://www.hl7.org/fhir/R4/domainresource.html" Target="_blank">FHIR domain resources</a>.

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
        <td>In the UK Core the format is the following, with the BusinessName in PascalCase:<br/><br/><code>https://fhir.hl7.org.uk/ValueSet/UKCore-<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
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
        <td>This will follow the  <a href="https://semver.org/" Target="_blank">Semantic Versioning standard</a> <code><i>&lsqb;major.minor.patch&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format is PascalCase:<br/><br/><code>UKCore<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format is Proper Case:<br/><br/><code>UK Core <i>&lsqb;Business Names&rsqb;</i></code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>See {{pagelink:NamingSystem.status}} for more information.</td>
    </tr>
    <tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in the UK Core.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all UK Core ValueSets, where the base URL is <code>https://fhir.hl7.org.uk</code>, this will be <code>HL7 UK</code>.</td>
    </tr>
        <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all UK Core ValueSets, where the base URL is <code> https://fhir.hl7.org.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The UKCore preference can be found under the {{pagelink:ValueSet-Descriptions}} section.</td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>All UK Core ValueSets SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    </tbody>
</table>

### Resource ValueSet - Content

View further information about <a href="https://hl7.org/fhir/R4/valueset.html" Target="_blank">Resource ValueSet - Content</a>.

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
        <td>compose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>BackboneElement</td>
        <td>See the {{pagelink:Content-Logical-Definition}} for details on how to populate this.</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.concept<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This element SHALL be used in the UKCore</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.filter<br>.property</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For UK Core ValueSets containing SNOMED CT concepts encapsulated within an ECL expression, the <code>constraint</code> value SHALL used.</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.filter<br>.value</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Due to some systems having difficulties processing symbols, for UK Core ValueSets containing SNOMED CT concepts encapsulated within an ECL expression, the long syntax SHALL be used. The SNOMED CT term SHALL NOT be suffixed to the SCTID.</td>
        </tr> 
  </tbody>
</table>

---

