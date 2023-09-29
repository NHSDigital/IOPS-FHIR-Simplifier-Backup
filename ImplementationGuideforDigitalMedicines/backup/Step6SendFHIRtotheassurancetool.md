### {{page-title}}

#### Setting up a collection

We recommend setting up a collection of queries to enable you to easily locate which are you need to test. 

For example:

{{render: api-client-collection}}

#### Endpoints

<table data-no-sort class="nhsd-!t-margin-bottom-7">
    <thead >
        <th>FHIR</td>
        <th>Resource</th>
        <th>Method</th>
        <th>Url</th>
    </thead>
    <tbody>
        <!-- R4 - MediationRequest -->
        <tr>
            <td>R4</td>
            <td>MedicationRequest</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/R4/MedicationRequest</td>
        </tr>
        <!-- R4 - MediationDispense -->
        <tr>
            <td>R4</td>
            <td>MedicationDispense</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/R4/MedicationDispense</td>
        </tr>
        <!-- R4 - MediationStatement -->
        <tr>
            <td>R4</td>
            <td>MedicationStatement</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/R4/MedicationStatement</td>
        </tr>
        <!-- STU3 - MediationRequest -->
        <tr>
            <td>STU3</td>
            <td>MedicationRequest</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/STU3/MedicationRequest</td>
        </tr>
        <!-- STU3 - MediationDispense -->
        <tr>
            <td>STU3</td>
            <td>MedicationDispense</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/STU3/MedicationDispense</td>
        </tr>
        <!-- STU3 - MediationStatement -->
        <tr>
            <td>STU3</td>
            <td>MedicationStatement</td>
            <td><code>POST</code></td>
            <td>http://192.168.128.27:8080/STU3/MedicationStatement</td>
        </tr>
    </tbody>
</table>

#### Headers

<table data-no-sort class="nhsd-!t-margin-bottom-7">
    <thead>
        <th>Key</th>
        <th>Value</th>
        <th>Description</td>
    </thead>
    <tbody>
        <!-- fromASID -->
        <tr>
            <td><code>fromASID</td>
            <td><code>{value}</code></td>
            <td>This will be provided in the email from the Self-Assurance Service Desk</td>
        </tr>
        <!-- toASID -->
        <tr>
            <td><code>toASID</code></td>
            <td><code>111111111111</code></td>
            <td>A test value not authenticated by the test tool</td>
        </tr>
        <!-- accept -->
        <tr>
            <td><code>Accept</code></td>
            <td><code>application/fhir+xml</code></td>
            <td>If using xml, <code>application/fhir+json</code>, if json</td>
        </tr>
        <!-- Content-Type -->
        <tr>
            <td><code>Content-Type</code></td>
            <td><code>application/fhir+xml</code></td>
            <td>If using xml, <code>application/fhir+json</code>, if json</td>
        </tr>
    </tbody>
</table>

#### Sending FHIR

Paste the appropriate FHIR within each query into the request `body` are of the API client.
Ensure that the type is apporprioately set (e.g. `xml` or `json`).

Press **Send**.

Providing you're connected to OpenTest, and have setup the headers correctly, you will receive a `201: No Content` response from the assurance tool.

#### Example `MedicationRequest` XML payload

```xml
<?xml version="1.0" encoding="utf-16"?>
<MedicationRequest>
  <id value="urn:med-req-1023938" />
  <status value="active" />
  <intent value="order" />
  <category>
    <coding>
      <system value="http://terminology.hl7.org/CodeSystem/medicationrequest-category" />
      <code value="inpatient" />
      <display value="inpatient" />
    </coding>
  </category>
  <medicationReference>
    <reference value="urn:medication-38769117" />
    <display value="Amoxicillin" />
  </medicationReference>
  <subject>
    <reference value="urn:patient-011223344" />
    <display value="Mrs Anne Teak" />
  </subject>
  <authoredOn value="2020-05-15T15:00:00Z" />
  <requester>
    <reference value="urn:staff-1112" />
    <display value="Dr Maikeu Well" />
  </requester>
  <recorder>
    <reference value="urn:staff-1112" />
    <display value="Dr Maikeu Well" />
  </recorder>
  <dosageInstruction>
    <timing>
      <repeat>
        <frequency value="3" />
        <period value="1" />
        <periodUnit value="d" />
      </repeat>
    </timing>
    <route>
      <coding>
        <system value="http://snomed.info/sct" />
        <code value="26643006" />
        <display value="oral" />
      </coding>
    </route>
    <doseAndRate>
      <doseQuantity>
        <value value="500" />
        <unit value="milligram" />
        <system value="http://unitsofmeasure.org" />
        <code value="mg" />
      </doseQuantity>
    </doseAndRate>
  </dosageInstruction>
  <substitution>
    <allowedBoolean value="false" />
  </substitution>
</MedicationRequest>
```

---