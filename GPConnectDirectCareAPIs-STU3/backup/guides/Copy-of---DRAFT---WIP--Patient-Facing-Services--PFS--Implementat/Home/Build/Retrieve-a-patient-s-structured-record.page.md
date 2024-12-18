## {{page-title}}

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> This is an upcoming 1.x (STU3) version of GP Connect API for building the Access Record Structured Document capabilities. This is a beta release and is open to change as suppliers develop against this specification and feedback is received. For other capabilities, please visit <a href="https://digital.nhs.uk/services/gp-connect/develop-gp-connect-services/specifications-for-developers">GP Connect specifications page</a>.
</div>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Summary:</b> Retrieve a patient's record in structured format.
</div>

## Use case

Retrieve a patient's record in FHIR&reg; structured format from a GP practice.

## Security

- GP Connect utilises TLS Mutual Authentication for system level authorization
- GP Connect utilises JSON Web Tokens (JWT) to transmit clinical audit and provenance details

## Prerequisites

### Consumer

The consumer system:
- **MUST** have previously traced the patient's NHS Number using the [Personal Demographics Service](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir) or an equivalent service

## API usage

### Interaction diagram

{{render: apiusage}}

### Request operation

#### FHIR&reg; relative request

```
POST /Patient/$gpc.getstructuredrecord
```

#### FHIR&reg; absolute request

```
POST https://[proxy_server]/https://[structured_provider_server]/gp-connect/patient-facing/gp-connect-acccess-record-fhir/
FHIR/STU3/Patient/$gpc.getstructuredrecord
```

#### Request headers

Consumers **MUST** include the following additional HTTP request headers:

| Header               | Value | Example |
|----------------------|-------|---------|
| `Authorization`      | An OAuth 2.0 bearer token. Required in all environments except sandbox. | `Bearer g1112R_ccQ1Ebbb4gtHBP1aaaNM`|
| `X-Correlation-ID` | An optional ID which you can use to track transactions across multiple systems. It can have any value, but we recommend avoiding . characters. Mirrored back in a response header. |`11C46F5F-CDEF-4865-94B2-0EE0EDCC26DA`|
| `X-Request-ID` | A globally unique identifier (GUID) for the request, which we use to de-duplicate repeated requests and to trace the request if you contact our helpdesk. Must be a universally unique identifier (UUID) (ideally version 4). | `0E0B220-8136-4CA5-AE46-1D97EF59D068`|

#### Payload request body ####

The payload request body comprises a `Parameters` resource, conforming to the [GPConnect-GetStructuredRecord-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-GetStructuredRecord-Operation-1/_history/1.15) `OperationDefinition` profile.

The `Parameters` resource is populated with the parameters shown below.  Note: The ↳ character indicates a part parameter.

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Optionality</th>
      <th>Cardinality</th>
      <th>Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">patientNHSNumber</code></td>
      <td><code class="highlighter-rouge">Identifier</code></td>
      <td>Mandatory</td>
      <td>1..1</td>
      <td>NHS Number of the patient for whom to retrieve the structured record.</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeAllergies</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include allergies and intolerances in the response.</td>
    </tr>
    <tr>
      <td>&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">includeResolvedAllergies</code></td>
      <td><code class="highlighter-rouge">Boolean</code></td>
      <td>Mandatory</td>
      <td>1..1</td>
      <td>
        Include resolved allergies and intolerances in the response.
        <p><i>Part parameter: may only be provided if <code>includeAllergies</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeMedication</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include medication in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">includePrescriptionIssues</code></span></td>
      <td><code class="highlighter-rouge">Boolean</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Include each prescription issue in the response, this parameter has a default value of 'true'. More guidance relating to its use is available in the <a href="https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medication_guidance.html">Medication guidance page</a>
        <p><i>Part parameter: may only be provided if <code>includeMedication</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td>&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">medicationSearchFromDate</code></td>
      <td><code class="highlighter-rouge">Date</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict medications returned on or after the date specified. Rules:
        <ul>
			<li>If the <code>medicationSearchFromDate</code> is not specified, all medication will be returned.</li>
			<li>If the <code>medicationSearchFromDate</code> is populated, all medications which are active on or after the <code>medicationSearchFromDate</code> <b>MUST</b> be returned.</li>
			<li><code>medicationSearchFromDate</code> <b>MUST</b> be populated with a date less than or equal to the current date.</li>
	        <li><code>medicationSearchFromDate</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
    	</ul>
    	<p><i>Part parameter: may only be provided if <code>includeMedication</code> is set.</i></p>
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeConsultations</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include consultations in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">consultationSearchPeriod</code></span></td>
      <td><code class="highlighter-rouge">Period</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict consultations by defining a time period
        <ul>
			     <li>If the <code>consultationSearchPeriod</code> is not specified, all consultations will be returned.</li>
			     <li>If the <code>consultationSearchPeriod.start</code> is populated, all consultations on or after the <code>consultationSearchPeriod.start</code> <b>MUST</b> be returned.</li>
           <li>If the <code>consultationSearchPeriod.end</code> is populated, all consultations on or before the <code>consultationSearchPeriod.end</code> <b>MUST</b> be returned.</li>
           <li><code>consultationSearchPeriod.start</code> and <code>consultationSearchPeriod.end</code> <b>MUST</b> be populated with a date less than or equal to the current date.</li>
          <li><code>consultationSearchPeriod.start</code> and <code>consultationSearchPeriod.end</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
    	</ul>
        <p><i>Part parameter: may only be provided if <code>includeConsultations</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">includeNumberOfMostRecent</code></span></td>
      <td><code class="highlighter-rouge">positiveInt</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Limit the number of returned consultations
        <p><i>Part parameter: may only be provided if <code>includeConsultations</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeProblems</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..*</td>
      <td>Include problems in the response. This is a repeating parameter with each repetition representing a pair of problem significance and status values.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">filterStatus</code></span></td>
      <td><code class="highlighter-rouge">Code</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict the problems that are returned by their clinical status. <br/>
        Valueset: <a href="http://hl7.org/fhir/stu3/valueset-condition-clinical.html">http://hl7.org/fhir/stu3/valueset-condition-clinical.html</a> Values <b>MUST</b> be <code>`active`</code> or <code>`inactive`</code><br/>
        <p><i>Part parameter: may only be provided if <code>includeProblems</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">filterSignificance</code></span></td>
      <td><code class="highlighter-rouge">Code</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict the problems that are returned by their clinical significance<br/>
        Valueset: <a href="https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ProblemSignificance-1">ValueSet-CareConnect-ProblemSignificance-1</a><br/>
        <p><i>Part parameter: may only be provided if <code>includeProblems</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeImmunisations</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include immunisations in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">includeNotGiven</code></span></td>
      <td><code class="highlighter-rouge">Boolean</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Only include immunisations that have been given in the response. The default value for this is <code>false</code>.
        <p><i>Part parameter: may only be provided if <code>includeImmunisations</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">includeStatus</code></span></td>
      <td><code class="highlighter-rouge">Boolean</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Include information about consent and dissent for immunisations in the response. The default value for this is <code>true</code>.
        <p><i>Part parameter: may only be provided if <code>includeImmunisations</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeUncategorisedData</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include uncategorised data in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">uncategorisedDataSearchPeriod</code></span></td>
      <td><code class="highlighter-rouge">Period</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict uncategorised data by defining a time period
        <ul>
			     <li>If the <code>uncategorisedDataSearchPeriod</code> is not specified, all uncategorised data will be returned.</li>
			     <li>If the <code>uncategorisedDataSearchPeriod.start</code> is populated, all uncategorised data on or after the <code>uncategorisedDataSearchPeriod.start</code> <b>MUST</b> be returned.</li>
           <li>If the <code>uncategorisedDataSearchPeriod.end</code> is populated, all uncategorised data on or before the <code>uncategorisedDataSearchPeriod.end</code> <b>MUST</b> be returned.</li>
           <li><code>uncategorisedDataSearchPeriod.start</code> and <code>uncategorisedDataSearchPeriod.end</code> <b>MUST</b> be populated with a date less than or equal to the current date.</li>
          <li><code>uncategorisedDataSearchPeriod.start</code> and <code>uncategorisedDataSearchPeriod.end</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
    	</ul>
        <p><i>Part parameter: may only be provided if <code>includeUncategorisedData</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeInvestigations</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include investigations in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">investigationSearchPeriod</code></span></td>
      <td><code class="highlighter-rouge">Period</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict test results by defining a time period
        <ul>
           <li>If the <code>investigationSearchPeriod</code> is not specified, all test results will be returned.</li>
           <li>If the <code>investigationSearchPeriod.start</code> is populated, all test results on or after the <code>investigationSearchPeriod.start</code> <b>MUST</b> be returned.</li>
           <li>If the <code>investigationSearchPeriod.end</code> is populated, all test results on or before the <code>investigationSearchPeriod.end</code> <b>MUST</b> be returned.</li>
           <li><code>investigationSearchPeriod.start</code> and <code>investigationSearchPeriod.end</code> <b>MUST</b> be populated with a date less than or equal to the current date.</li>
          <li><code>investigationSearchPeriod.start</code> and <code>investigationSearchPeriod.end</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
      </ul>
        <p><i>Part parameter: may only be provided if <code>includeInvestigations</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeReferrals</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include referrals in the response.</td>
    </tr>
    <tr>
      <td><span style="white-space: nowrap;">&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">referralSearchPeriod</code></span></td>
      <td><code class="highlighter-rouge">Period</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict referrals by defining a time period
        <ul>
           <li>If the <code>referralSearchPeriod</code> is not specified, all referrals will be returned.</li>
           <li>If the <code>referralSearchPeriod.start</code> is populated, all referrals on or after the <code>referralSearchPeriod.start</code> <b>MUST</b> be returned.</li>
           <li>If the <code>referralSearchPeriod.end</code> is populated, all referrals on or before the <code>referralSearchPeriod.end</code> <b>MUST</b> be returned.</li>
           <li><code>referralSearchPeriod.start</code> and <code>referralSearchPeriod.end</code> <b>MUST</b> be populated with a date less than or equal to the current date.</li>
          <li><code>referralSearchPeriod.start</code> and <code>referralSearchPeriod.end</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
      </ul>
        <p><i>Part parameter: may only be provided if <code>includeReferrals</code> is set.</i></p>        
      </td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">includeDiaryEntries</code></td>
      <td><code class="highlighter-rouge"></code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>Include diary entries in the response.</td>
    </tr>
    <tr>
      <td>&nbsp;&nbsp;&#8627; <code class="highlighter-rouge">diaryEntriesSearchDate</code></td>
      <td><code class="highlighter-rouge">Date</code></td>
      <td>Optional</td>
      <td>0..1</td>
      <td>
        Restrict diary entries returned on or before the date specified. Rules:
        <ul>
      <li>If the <code>diaryEntriesSearchDate</code> is not specified, all diary entries will be returned.</li>
      <li>If the <code>diaryEntriesSearchDate</code> is populated, all diary entries which occur on or before the <code>diaryEntriesSearchDate</code> <b>MUST</b> be returned.</li>
      <li><code>diaryEntriesSearchDate</code> <b>MUST</b> be populated with a date greater than or equal to the current date.</li>
          <li><code>diaryEntriesSearchDate</code> <b>MUST</b> be populated with whole dates only (for example, 2017-02-01) - that is, no partial dates, or with a time period or offset.</li>
      </ul>
      <p><i>Part parameter: may only be provided if <code>includeDiaryEntries</code> is set.</i></p>
      </td>
    </tr>
  </tbody>
</table>

Each clinical area has its own set of search/filter parameters. These parameters will only apply to their own area and **MUST** have no impact on other parameters.

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> Consumer guidance: The parameters can be used together in a single call or in multiple calls so that information can be retrieved if required. It is advised that the number of requests that are made to retrieve a patient's record are kept to a minimum.
</div>

The example below shows a fully populated `Parameters` resource as a request to the `$gpc.getstructuredrecord` operation:

```
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeAllergies",
      "part": [
        {
          "name": "includeResolvedAllergies",
          "valueBoolean": true
        }
      ]
    },
    {
      "name": "includeMedication",
      "part": [
        {
          "name": "medicationSearchFromDate",
          "valueDate": "2017-06-04"
        },
        {
          "name": "includePrescriptionIssues",
          "valueDate": true
        }
      ]
    },
    {
      "name": "includeConsultations",
      "part": [
        {
          "name": "consultationSearchPeriod",
          "valuePeriod": {
            "start": "2017-12-25",
            "end": "2018-12-25"
          }
        },
        {
          "name": "includeNumberOfMostRecent",
          "valuePositiveInt": 3
        }
      ]
    },
    {
      "name": "includeProblems",
      "part": [
        {
          "name": "filterStatus",
          "valueCode": "active"
        },
        {
          "name": "filterSignificance",
          "valueCode": "major"
        }
      ]
    },
    {
      "name": "includeImmunisations",
      "part": [
        {
          "name": "includeNotGiven",
          "valueBoolean": false
        },
        {
          "name": "includeStatus",
          "valueBoolean": false
        }
      ]
    },
    {
      "name": "includeUncategorisedData",
      "part": [
        {
          "name": "uncategorisedDataSearchPeriod",
          "valuePeriod": {
            "start": "2016-12-25",
            "end": "2018-12-25"
          }
        }
      ]
    },
    {
      "name": "includeInvestigations",
      "part": [
        {
          "name": "investigationSearchPeriod",
          "valuePeriod": {
            "start": "2017-01-02",
            "end": "2017-07-02"
          }
        }
      ]
    },
    {
      "name": "includeReferrals",
      "part": [
        {
          "name": "referralSearchPeriod",
          "valuePeriod": {
            "start": "2016-12-25",
            "end": "2018-12-25"
          }
        }
      ]
    },
    {
      "name": "includeDiaryEntries",
      "part": [
        {
          "name": "diaryEntriesSearchDate",
          "valueDate": "2017-06-04"
        }
      ]
    }
  ]
}
```

##### Not permitted parameter combinations

Certain combinations of query parameters have the potential to introduce clinical risks. To prevent these scenarios occurring, the following combinations of parameters are not permitted and **SHALL** not be used by consumers:

When requesting consultations, the following part parameters **MUST NOT** be included:
  - `includeMedication.medicationSearchFromDate`
  - `includeUncategorisedData.uncategorisedDataSearchPeriod`
  - `includeProblems.filterSignificance`
  - `includeProblems.filterStatus`
  - `includeReferrals.referralSearchPeriod`
  - `includeDiaryEntries.diaryEntriesSearchDate`
  - `includeImmunisations.includeNotGiven`
  - `includeImmunisations.includeStatus`  

When requesting problems, the following part parameters **MUST NOT** be included:
  - `includeMedication.medicationSearchFromDate`
  - `includeUncategorisedData.uncategorisedDataSearchPeriod`
  - `includeReferrals.referralSearchPeriod`
  - `includeDiaryEntries.diaryEntriesSearchDate`
  - `includeImmunisations.includeNotGiven`
  - `includeImmunisations.includeStatus`    

In the event that one of the combinations of parameters are used in a request, an error **MUST** be raised as specified in the error handling table below. There are no restrictions on using combinations of top level parameters.

Examples of queries are available on the [Search examples](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_searchExamples.html) page.

#### Related problem headers not returned due to search criteria

If a problem is related to another problem using the `relatedProblemHeader` extension it is possible that the related problem header is not returned due to the restrictions of the search criteria. It is possible for many problems to be related to each other and if the user needs to fully understand the problem relationships these can be returned by requesting all problems.  This is done by not specifying a filter for significance or status and putting `includeProblems` in the request. This will result in all problems recorded on the GP system being returned and will include all links between problems.

#### Error handling

The provider system **MUST** return a [GPConnect-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1/_history/1.2) resource that provides additional detail when one or more data field is corrupt or a specific business rule/constraint is breached.

The table below shows common errors that may be encountered during this API call, and the returned Spine error code.  Please see [Error handling guidance](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html) for additional information needed to create the error response, or to determine the response for errors encountered that are not shown below.

Errors returned due to parameter failure **MUST** include diagnostic information detailing the invalid parameter.

| Error encountered | Spine error code returned |
|-|-|
| The `Parameters` resource passed does not conform to that specified in the [GPConnect-GetStructuredRecord-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-GetStructuredRecord-Operation-1/_history/1.13) `OperationDefinition` | [`INVALID_RESOURCE`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The provider could not parse the `Parameters` resource. | [`INVALID_RESOURCE`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| No recognised parameters are provided | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `patientNHSNumber` parameter is not provided | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `patientNHSNumber` parameter value is invalid, for example it fails format or check digit tests | [`INVALID_NHS_NUMBER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The `medicationSearchFromDate` part parameter contains a partial date, or has a value containing a time or offset component | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `medicationSearchFromDate` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `includeAllergies` parameter is passed without the corresponding `includeResolvedAllergies` part parameter | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The start date of the `consultationSearchPeriod` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The end date of the `consultationSearchPeriod` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The start date of the `consultationSearchPeriod` part parameter is greater than the end date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `consultationSearchPeriod` and `includeNumberOfMostRecent` part parameters are both populated | [`INVALID_RESOURCE`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The start date of the `uncategorisedDataSearchPeriod` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The end date of the `uncategorisedDataSearchPeriod` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The start date of the `uncategorisedDataSearchPeriod` part parameter is greater than the end date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `filterStatus` part parameter contains a value other than `active` or `inactive` | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `filterSignificance` part parameter contains a value other than `major` or `minor` | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `investigationSearchPeriod` parameter value contains a partial date, or has a value containing a time or offset component | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `referralSearchPeriod` part parameter is greater than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The patient has dissented to sharing their clinical record | [`NO_PATIENT_CONSENT`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#security-validation-errors) |
| A patient could not be found matching the `patientNHSNumber` provided | [`PATIENT_NOT_FOUND`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The request is for the record of an [inactive](https://developer.nhs.uk/apis/gpconnect-1-5-1/overview_glossary.html#active-patient) or deceased patient | [`PATIENT_NOT_FOUND`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The request is for the record of a non-Regular/GMS patient (i.e. the patient’s registered practice is somewhere else) | [`PATIENT_NOT_FOUND`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The patient's NHS number in the provider system is not associated with an NHS number status indicator code of 'Number present and verified' | [`PATIENT_NOT_FOUND`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The request is for a sensitive patient | [`PATIENT_NOT_FOUND`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#identity-validation-errors) |
| The `diaryEntriesSearchDate` part parameter contains a partial date, or has a value containing a time or offset component | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| The `diaryEntriesSearchDate` part parameter is less than the current date | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| A part parameter is passed without a value | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| A combination of parameters is included that isn't permitted | [`INVALID_PARAMETER`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#resource-validation-errors) |
| GP Connect is not enabled at the practice (see [Enablement](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_api_non_functional_requirements.html#enablement)) | [`ACCESS DENIED`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#security-validation-errors) |
| The Get Record capability is not enabled at the practice (see [Enablement](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_api_non_functional_requirements.html#enablement)) | [`ACCESS DENIED`](https://developer.nhs.uk/apis/gpconnect-1-5-1/development_fhir_error_handling_guidance.html#security-validation-errors) |

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> The HL7 FHIR specification states that Parameters.parameter MUST have one of part, value or resource. However, in the case of Parameters which just have optional part parameters such as `includeProblems` it is valid to have no part parameters or value in a request. The following is an example of the `includeProblems` parameter with no part parameters:
</div>


```
{
  "name": "includeProblems"
}
```

### Request response

#### Response headers

```
HTTP/1.1 200 OK
Cache-Control: no-store
Content-Type: application/fhir+json; charset=utf-8
Date: Sun, 07 Aug 2016 11:13:05 GMT
Content-Length: 1464
```

#### Payload response body

Provider systems **MUST**:

- return a `200` **OK** HTTP status code to indicate successful retrieval of a patient's structured record
- return a `Bundle` conforming to the [`GPConnect-StructuredRecord-Bundle-1`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-Searchset-Bundle-1?version=current) profile definition
- return the following resources in the `Bundle`:
  - `Patient` matching the NHS Number sent in the body of the request
  - `Organization` matching the patient's registered GP practice, referenced from `Patient.generalPractitioner`
  - `Organization` matching the organisation serving the request, if different from above, referenced from `Patient.managingOrganization`
  - `Practitioner` matching the patient's usual GP, if they have one, referenced from `Patient.generalPractitioner`
  - `PractitionerRole` matching the usual GP's role
  - resources holding consultations, problems, immunisations, allergies, intolerance, medications, uncategorised data, referrals, investigations, diary entries and warnings about unsupported parameters according to the rules below:

Provider systems **SHOULD**:

- provide a consistent order to elements within the `Bundle` resource.  It is recommended to follow the order described in the Bundle population illustrated diagram.

Consumers systems **MUST NOT**:

- rely on order or index of elements within the `Bundle` resource in order to parse encapsulated resources.

##### Unavailability of data
There are scenarios where requested clinical areas may not be returned, these are listed on the  [Configuration for supported clinical areas](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_clinical_area_config.html) page along with guidance on implementation. Consumer systems **MUST** be able to handle this unavailability and warn users that some information hasn't been returned.

##### Allergies

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeAllergies` parameter is not set:

  - no allergy or intolerance information shall be returned

- when the `includeAllergies` parameter is set:

  - and when the `includeResolvedAllergies` parameter is set to `false`:

    - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources that match the supplied query parameters
    - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources
    - [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) and [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources representing the patient's allergies and intolerances, <i>excluding</i> those marked as resolved or ended

  - and when the `includeResolvedAllergies` parameter is set to `true`:

    - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources that match the supplied query parameters
    - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources
    - [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) and [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources representing the patient's allergies and intolerances, <i>including</i> those marked as resolved or ended

- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the &nbsp; [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources

<br/>

##### Medications

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeMedication` parameter is not set:

  - no medication information shall be returned

- when the `includeMedication` parameter is set:

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html) resources
  - [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html), [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html), [`MedicationRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationrequest.html) with an `intent` of `plan` and &nbsp; [`Medication`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medication.html) resources representing the patient's medication summary information (authorisations and medication prescribed elsewhere)

  - when the `medicationSearchFromDate` parameter is set:
	- all medications which are active on or after the `medicationSearchFromDate` **MUST** be returned
	  - A medication is considered active between its `effective.start` and `effective.end` (inclusive)
		  - when a medication **does not** have an `effective.end`:
			- an acute medication is considered active on its `effective.start` only
			- a repeat medication is considered on-going and is active from its `effective.start`
			- when a medication is not defined as an acute or repeat it **MUST** be treated as repeat
  - all medications that are prescribed elsewhere will be returned regardless of the `medicationSearchFromDate`

  - and when the `includePrescriptionIssues` parameter is set to `false`:

    - no prescription issue information should be returned

  - and when the `includePrescriptionIssues` parameter is set to `true` or not included:

    - [`MedicationRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationrequest.html) resources with an `intent` of `order` representing the patient's prescription issues, for the above medication summary data

- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the &nbsp; [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html) and &nbsp; [`MedicationRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationrequest.html) resources

<br/>

##### Consultations

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeConsultations` parameter is not set:

  - no consultation information shall be returned

- when the `includeConsultations` parameter is set:
- A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource for each clinical area referencing resources that have been returned
- A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource for secondary lists referencing resources contained in requested problems and consultations

- [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html), [`MedicationRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationrequest.html), [`Medication`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medication.html) resources representing the patient's medication
- [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources representing the patient's allergies and intolerances
- [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html), [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html), [`Encounter`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_encounter.html), [`List - Consultation`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list_consultation.html) and [`Observation - narrative`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_guidance_observation_narrative.html) resources representing the patient's consultations
- [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources representing the patient's problems
- [`Immunization`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_immunization.html) resources representing the patient's immunisations
- [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) and [`Observation - blood pressure`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_bloodPressure.html) resources representing the patient's uncategorised data
- [`DiagnosticReport`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_DiagnosticReport.html), [`Observation - Test Group Header`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testGroup.html), [`Observation - Test Result`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testResult.html), [`Observation - Filing Comments`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_filingComments.html), [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_ProcedureRequest.html), [`Specimen`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_specimen.html) resources representing the patient's test results
- [`ReferralRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_referralrequest.html) resources representing the patient's referrals will be returned.
- [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_diaryentry.html) resources representing the patient's diary entries will be returned.
- [`DocumentReference`](https://developer.nhs.uk/apis/gpconnect-1-5-1/access_documents_development_documentreference.html) resources representing the patient's documents.
  - and when the `numberOfMostRecent` parameter is set:
    - limit the number of returned consultations to match the included value

- when the `consultationSearchPeriod` is set:
  - when a `start` value is set, all consultations with an `Encounter.period.start` after the date **MUST** be returned
  - and when an `end` value is set, all consultations with an `Encounter.period.end` before the date **MUST** be returned
  - and when both a `start` and `end` are specified, consultations with an `Encounter.period.start` after the `start` and an `Encounter.period.end` before the `end` **MUST** be returned

- when the `includeNumberOfMostRecent` is set:
  - consultations **MUST** be ordered by `Encounter.period.start` descending
  - and the number of most recent consultations matching the parameter value **MUST** be returned

- `Organization`, `Practitioner`, `PractitionerRole` and `Location` resources that are referenced by the above resources that represent the consultation and its linked information

##### Problems

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeProblems` parameter is not set:

  - no problem information shall be returned

- when the `includeProblems` parameter is set:

- A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource for each clinical area referencing resources that have been returned
- A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource for secondary lists referencing resources contained in requested problems and consultations

- [`MedicationStatement`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationstatement.html), [`MedicationRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medicationrequest.html), [`Medication`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_medication.html) resources representing the patient's medication
- [`AllergyIntolerance`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_allergyintolerance.html) resources representing the patient's allergies and intolerances
- [`Encounter`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_encounter.html) resources representing the patient's consultations
- [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources representing the patient's problems
- [`Immunization`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_immunization.html) resources representing the patient's immunisations
- [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) and [`Observation - blood pressure`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_bloodPressure.html) resources representing the patient's uncategorised data
- [`DiagnosticReport`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_DiagnosticReport.html), [`Observation - Test Group Header`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testGroup.html), [`Observation - Test Result`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testResult.html), [`Observation - Filing Comments`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_filingComments.html), [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_ProcedureRequest.html), [`Specimen`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_specimen.html) resources representing the patient's test results
- [`ReferralRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_referralrequest.html) resources representing the patient's referrals will be returned.
-[`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_diaryentry.html) resources representing the patient's diary entries will be returned.
- [`DocumentReference`](https://developer.nhs.uk/apis/gpconnect-1-5-1/access_documents_development_documentreference.html) resources representing the patient's documents.

- and when the `filterStatus` parameter is set:

  - problems with a `clinicalStatus` matching the parameter value and all linked clinical information.

- and when the `filterSignificance` parameter is set:

  - problems with a `problemSignificance` matching the parameter value and all linked clinical information

- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the above resources that represent the problem and its linked information

##### Immunisations

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeImmunisations` parameter is not set:

  - no immunisation information shall be returned

- when the `includeImmunisations` parameter is set:

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Immunization`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_immunization.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`Immunization`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_immunization.html) resources
  - [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) and [`Immunization`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_immunization.html) resources representing the patient's immunisations that have been given will be returned.

  - and when the `includeNotGiven` part parameter is set to `false` or not supplied:

    - only immunisations where `notGiven` is set to `false` shall be returned

  - and when the `includeNotGiven` part parameter is set to `true`

    - all immunisations where `notGiven` is set to `true` or `false` shall be returned

  - and when the `includeStatus` part parameter is set to `false`:

    - only immunisations will be returned

  - and when the `includeStatus` part parameter is set to `true` or not supplied:

    - [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) resources representing the status of patient's immunisations will also be returned.

- `Organization`, `Practitioner`, `PractitionerRole` and `Location` resources that are referenced by the above resources that represent the immunization and its linked information

##### Uncategorised data

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeUncategorisedData` parameter is not set:

  - no uncategorised data shall be returned

- when the `includeUncategorisedData` parameter is set:

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) resources
  - [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html), [`Observation - uncategorised`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_uncategorisedData.html) and [`Observation - blood pressure`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_bloodPressure.html) resources representing the patient's uncategorised data will be returned.

- when the `uncategorisedDataSearchPeriod` is set:
  - when a `start` value is set, all uncategorised data with an `Observation.effectiveTime` after the date **MUST** be returned
  - and when an `end` value is set, all uncategorised data with an `Observation.effectiveTime` before the date **MUST** be returned
  - and when both a `start` and `end` are specified, uncategorised data with an `Observation.effectiveTime` after the `start` and with an `Observation.effectiveTime` before the `end` **MUST** be returned

- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the above resources that represent the uncategorised data and its linked information

##### Investigations

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeInvestigations` parameter is not set:

  - no investigations shall be returned

- when the `includeInvestigations` parameter is set:

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`DiagnosticReport`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_DiagnosticReport.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`DiagnosticReport`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_DiagnosticReport.html) resources
  - [`DiagnosticReport`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_DiagnosticReport.html), [`Observation - Test Group Header`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testGroup.html), [`Observation - Test Result`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_testResult.html), [`Observation - Filing Comments`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_observation_filingComments.html), [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_ProcedureRequest.html), [`Specimen`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_specimen.html) and &nbsp; [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources representing the patient's test results

  - and when the `investigationSearchPeriod` parameter is set:
    - when a `start` value is set, all investigations with a `DiagnosticReport.issued` after the date **MUST** be returned
    - and when an `end` value is set, all investigations with a `DiagnosticReport.issued` before the date **MUST** be returned
    - and when both a `start` and `end` are specified, investigations with a `DiagnosticReport.issued` after the `start` and before the `end` **MUST** be returned


- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the above resources that represent the uncategorised data and its linked information

##### Referrals

Provider systems **MUST** include the following in the response `Bundle`:

- when the `includeReferrals` parameter is not set:

  - no referrals information shall be returned

- when the `includeReferrals` parameter is set:

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`ReferralRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_referralrequest.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`ReferralRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_referralrequest.html) resources
  - [`ReferralRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_referralrequest.html), [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) and [`DocumentReference`](https://developer.nhs.uk/apis/gpconnect-1-5-1/access_documents_development_documentreference.html) resources representing the patient's referrals will be returned

- when the `referralSearchPeriod` is set:
  - when a `start` value is set, all referrals with a `ReferralRequest.authoredOn` after the date **MUST** be returned
  - and when an `end` value is set, all referrals with a `ReferralRequest.authoredOn` before the date **MUST** be returned
  - and when both a `start` and `end` are specified, referrals with a `ReferralRequest.authoredOn` after the `start` and with a `ReferralRequest.authoredOn` before the `end` **MUST** be returned

- `Organization`, `Practitioner`, `PractitionerRole` and `HealthcareService` resources that are referenced by the above resources that represent the referral and its linked information

  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_diaryentry.html) resources that match the supplied query parameters
  - A [`List`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_list.html) resource referencing [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources that are linked from the returned [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_diaryentry.html) resources
  - [`ProcedureRequest`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_development_diaryentry.html) and [`Condition`](https://developer.nhs.uk/apis/gpconnect-1-5-1/accessrecord_structured_problems.html) resources representing the patient's diary entries will be returned

- when the `diaryEntriesSearchDate` parameter is set:
  - all diary entries that occur on or before the `diaryEntriesSearchDate` **MUST** be returned

- `Organization`, `Practitioner` and `PractitionerRole` resources that are referenced by the above resources that represent the diary entry and its linked information

#### Unknown and partial date handling in searches

Where parameters contain part parameters for date searches, the following **SHALL** apply:
- clinical information where an effective date is unknown or not recorded shall be returned alongside information that matches the supplied dates
- where partial dates have been recorded, they will be evaluated against the supplied dates in the following way:
  - Dates with only the year specified are equivalent to an interval that starts on the first instant of January 1st and ends on the last instant of December 31st
  - Dates with only the year and month specified are equivalent to an interval that starts at the first instant of the first day of the month and ends on the last instant of the last day of the month

#### Medication search date

The `medicationSearchFromDate` identifies the start date of the requested medications search period. An end date cannot be requested by a consumer, so that all searches go to the end of the patient's record.

The scenarios below represent how a selection of acute and repeat medications are returned based on the search date in the request. Each scenario has a different search date. Medications that have been greyed out are not returned in the response.

<ul id="profileTabs" class="nav nav-tabs">
    <li class="active"><a href="#scenario1" data-toggle="tab">Scenario 1</a></li>
    <li><a href="#scenario2" data-toggle="tab">Scenario 2</a></li>
    <li><a href="#scenario3" data-toggle="tab">Scenario 3</a></li>
	<li><a href="#scenario4" data-toggle="tab">Scenario 4</a></li>
</ul>
  <div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="scenario1">
<table class='resource-attributes'>
  <tr>
    <td style="font-size:14px"><b>Search date:</b> <code>15/01/2018</code></td>
	<td style="font-size:14px" align="right"><b>Current date:</b> <code>08/10/2018</code></td>
  </tr>
</table>

{{render: datafilterscenario1}}

</div>

<div role="tabpanel" class="tab-pane" id="scenario2">
<table class='resource-attributes'>
  <tr>
    <td style="font-size:14px"><b>Search date:</b> <code>01/03/2018</code></td>
	<td style="font-size:14px" align="right"><b>Current date:</b> <code>08/10/2018</code></td>
  </tr>
</table>

{{render: datafilterscenario2}}

</div>

<div role="tabpanel" class="tab-pane" id="scenario3">
<table class='resource-attributes'>
  <tr>
    <td style="font-size:14px"><b>Search date:</b> <code>08/07/2018</code></td>
	<td style="font-size:14px" align="right"><b>Current date:</b> <code>08/10/2018</code></td>
  </tr>
</table>

{{render: datafilterscenario3}}

</div>

<div role="tabpanel" class="tab-pane" id="scenario4">
<table class='resource-attributes'>
  <tr>
    <td style="font-size:14px"><b>Search date:</b> <code>08/10/2018</code></td>
	<td style="font-size:14px" align="right"><b>Current date:</b> <code>08/10/2018</code></td>
  </tr>
</table>

{{render: datafilterscenario4}}

</div>
</div>

<br/>

#### Bundle population illustrated

The following diagram illustrates the population of the response `Bundle` according to the parameters in the inbound `Parameters` request resource:

{{render: structuredbundleresponse}}

#### Payload response examples

Examples of the payload requests and responses can be found here:

- [Allergies - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Allergies?version=current)
- [Medication - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Medications?version=current)
- [Consultations and problems - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Consultations?version=current)
- [Immunizations - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Immunizations?version=current)
- [Uncategorised data - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Uncategorised-Data?version=current)
- [Investigations - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Investigations?version=current)
- [Referrals - FHIR&reg; examples](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Referrals?version=current)

To illustrate how forwards compatibility works, the following example has been included:
- [Retrieve consultations, problems, medications and allergies from a provider on version 1.2.3 of the GP Connect API](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Examples/Multiple-combined?version=current)