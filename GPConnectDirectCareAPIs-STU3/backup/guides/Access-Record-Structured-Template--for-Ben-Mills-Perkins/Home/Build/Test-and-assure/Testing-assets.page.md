## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Details of test resources made available to support the holistic testing of provider APIs and consumer applications
</div>

### Provider testing (SIT)

An automated provider test harness has been made publicly available to allow standardised testing of the FHIR® APIs prior to any formal assurance activities being undertaken. This approach aims to streamline the end-to-end assurance process by ensuring that a common baseline level of technical conformance has been achieved and, thus, fewer issues are surfaced during formal assurance.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Download</b>: Download the <a href="https://github.com/nhsconnect/gpconnect-provider-testing">GP Connect automated test suite for API providers</a> to help validate the technical conformance of your provider API implementation.
</div>

#### Provider testing layers

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>TO DO</b>: HAVE A CHAT WITH STEVE HUNT - TO DISCUSS THE NHS LOGIN TESTING (NOT WITH JWT & SSL)
</div>

<table data-responsive>
    <thead>
        <tr>
            <th>Category</th>
            <th>Layer</th>
            <th>Details</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Provider Capability</td>
            <td>API Orchestration</td>
            <td>Use Cases</td>
        </tr>
        <tr>
            <td>Provider Terminology</td>
            <td>API Data Layer</td>
            <td>Test Cases</td>
        </tr>
        <tr>
            <td>Technical</td>
            <td>API Payload(s)</td>
            <td>FHIR Profile Conformance, ValueSet Usage, Constraint Rules</td>
        </tr>
        <tr>
            <td>Technical</td>
            <td>API Conformance</td>
            <td>URL Format, URL Parameters, HTTP Error Handling</td>
        </tr>
        <tr>
            <td>Standards</td>
            <td>FHIR Conformance</td>
            <td>Metadata, RESTful, Identifier Handling, Search Patterns</td>
        </tr>
        <tr>
            <td>Technical</td>
            <td>Spine Integration</td>
            <td>SSL Certificate Handling, URL Format, SSP Headers</td>
        </tr>
        <tr>
            <td>Standards</td>
            <td>HTTP Conformance</td>
            <td>Accept Encodings, Transfer Encodings, ETags Compression</td>
        </tr>
        <tr>
            <td>Standards</td>
            <td>JWT Conformance</td>
            <td>Authentication, Claims, Auditing</td>
        </tr>
        <tr>
            <td>Standards</td>
            <td>SSL Conformance</td>
            <td>TLS Versions, Supported Ciphers, Client Authentication, Certificate Revocation</td>
        </tr>
    </tbody>
</table>

</br>

See the [GP Connect provider testing wiki](https://github.com/nhsconnect/gpconnect-provider-testing/wiki) for further details.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note:</b> Generic FHIR test harnesses such as <a href="https://github.com/FirelyTeam/sprinkler"> Sprinklr </a> and <a href="https://www.aegis.net/touchstone/">TouchStone</a> may also be of interest to implementers.
</div>

#### Non-functional

<table data-responsive>
    <thead>
        <tr>
            <th>Category</th>
            <th>Layer</th>
            <th>Details</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Security</td>
            <td>Penetration Testing</td>
            <td>OWASP Top 10</td>
        </tr>
        <tr>
            <td>Performance</td>
            <td>API Performance</td>
            <td>Response Times</td>
        </tr>
        <tr>
            <td>Volumetrics</td>
            <td>API TPS</td>
            <td>LOAD, RAMP, SOAK</td>
        </tr>
    </tbody>
</table>

</br>

### Consumer testing (SIT)

#### Consumer testing layers

An additional UI testing layer is required for consumer systems.

<table data-responsive>
    <thead>
        <tr>
            <th>Category</th>
            <th>Layer</th>
            <th>Details</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Consumer Capability</td>
            <td>UI Behaviours</td>
            <td>UI Use Case Automation</td>
        </tr>
</table>

</br>

#### Non-functional

<table data-responsive>
    <thead>
        <tr>
            <th>Category</th>
            <th>Layer</th>
            <th>Details</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Security</td>
            <td>Penetration Testing	</td>
            <td>OWASP Top 10</td>
        </tr>
</table>

</br>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b>: Formal V&P testing is not required for consumer applications.
</div>

---

</br>