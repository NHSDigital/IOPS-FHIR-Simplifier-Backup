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
        <td>In the UK Core the format is the following, with the BusinessName in PascalCase:<br/><br/><code>https://fhir.hl7.org.uk/CodeSystem/UKCore-<i>&lsqb;BusinessNames&rsqb;</i></code>.</td>
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
        <td>For all UK Core CodeSystems, where the base URL is <code>https://fhir.hl7.org.uk</code>, this will be <code>HL7 UK</code>.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>Contact details for the publisher.<br/><br/>See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all UK Core CodeSystems, where the base URL is <code> https://fhir.hl7.org.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>The UKCore format SHOULD be as follows:<br/><br/><samp>A set of codes that define &lsqb;description&rsqb;</samp>.</td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>
        All UK Core CodeSystems SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://hl7.org/fhir/R4/codesystem.html#CodeSystem" Target="_blank">FHIR Resource CodeSystem - Content</a>.

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
        <td>caseSensitive</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>boolean</td>
        <td>For all UK Core CodeSystems this SHALL be set to &quot;true&quot; unless a specific use case justifies it being set to &quot;false&quot;. In this case the reasoning for the decision SHALL be added to the description element.</td>
    </tr>
    <tr>
        <td>concept</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Backbone<br>Element</td>
        <td>Concepts that are in the code system.<br/><br/>Cardinality would normally be 1..* but set to the standard 0..* to allow for a use case where the content element has a value of &quot;not-present&quot;.</td>
    </tr>
    <tr>
        <td>concept<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>uri</td>
        <td>This SHALL be included as this presents the concept to a user in a human-readable manner.</td>
    </tr>
  </tbody>
</table>

<br><br>

---

