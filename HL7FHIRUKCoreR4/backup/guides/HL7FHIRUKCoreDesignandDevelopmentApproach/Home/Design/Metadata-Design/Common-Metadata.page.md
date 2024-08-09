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
        <td>In the UK Core the format is the following, with the FHIRAssetName and Specialism in PascalCase:<br/><br/><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-<i>[FHIRAssetName][Specialism]</i></code>.</td>
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
        <td>This will follow the  <a href="https://semver.org/" Target="_blank">Semantic Versioning standard</a> <code><i>[major.minor.patch]</i></code>.<br>
        Further details about <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/DevelopmentandPublication/UKCoreDevelopmentandReleaseManagement#FHIRAssetsVersioning" Target="_blank">internal versioning for UK Core assets</a> are available. </td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format is PascalCase:<br/><br/><code>UKCore<i>[FHIRAssetName][Specialism]</i></code> .</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In the UK Core the format is Proper Case:<br/><br/><code>UK Core <i>[FHIRAssetName] [Specialism]</i><code>.</td>
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
        <td>For all UK Core Profiles, where the base URL is <code>https://fhir.hl7.org.uk</code>, the name of the publisher will be <code>HL7 UK</code>.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>See {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all UK Core Profiles, where the base URL is <code> https://fhir.hl7.org.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>This SHALL be in the following format:<br><br>
        <samp>This profile defines the UK constraints and extensions on the International FHIR resource [FHIRAssetName](<i>[link to HL7 Resource]</i>).</samp></td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td> All UK Core Profiles SHALL contain the the copyright as listed in {{pagelink:Publisher--Contact---Copyright}}</td>
    </tr>