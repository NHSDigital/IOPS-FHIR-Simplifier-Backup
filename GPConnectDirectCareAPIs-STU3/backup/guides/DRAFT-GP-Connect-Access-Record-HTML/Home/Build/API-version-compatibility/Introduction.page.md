## {{page-title}}

The GP Connect API requires that a solution for forwards and backwards compatibility is developed as there is the potential for multiple versions of the GP Connect API to be implemented by consumers and providers.

### Forwards and backwards compatibility

#### Forwards compatibility

Forwards compatibility is the scenario where a consumer requests a higher version of the API than the provider supports. This requires that a provider **MUST** be able to warn a consumer when they don’t support a requested parameter or part parameter.

In this scenario, providers **MUST** respond in the following way:

- return a `200` **OK** HTTP status code to indicate successful retrieval of a patient’s structured record
- Include FHIR® resources for supported parameters
- as part of the returned bundle, include a single [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) with an `issue` for each unsupported parameter or part parameter where:
    - `issue.code` = `not-supported`
    - `issue.severity` = `warning`
    - `issue.details.coding.system` = `https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1`
    - `issue.details.coding.code` = `NOT_IMPLEMENTED`
    - `issue.details.coding.display` = `Not implemented`
- Where it’s an unsupported parameter the following **MUST** be supplied:
    - `issue.details.text` = `<parameter-name>` is an unrecognised parameter
    - `issue.diagnostics` = `<parameter-name>`
- Where it’s an unsupported part parameter the following **MUST** be supplied:
    - `issue.details.text` = `<parameter-name>.<part-parameter-name> is an unrecognised parameter`
    - `issue.diagnostics` = `<parameter-name>.<part-parameter-name>`

The example shows a fully populated [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) for a request where the `includeConsultations` and `includeProblems` parameters weren’t supported:

```json
{
  "resource": {
    "resourceType": "OperationOutcome",
    "id": "8b679981-e9be-4e37-b103-799295a6aec8",
    "meta": {
      "profile": [
        "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"
      ]
    },
    "issue": [
      {
        "severity": "warning",
        "code": "not-supported",
        "details": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1",
              "code": "NOT_IMPLEMENTED",
              "display": "Not implemented"
            }
          ],
          "text": "includeConsultations is an unrecognised parameter"
        },
        "diagnostics": "includeConsultations"
      },
      {
        "severity": "warning",
        "code": "not-supported",
        "details": {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1",
              "code": "NOT_IMPLEMENTED",
              "display": "Not implemented"
            }
          ],
          "text": "includeProblems is an unrecognised parameter",
        },
        "diagnostics": "includeProblems"
      }
    ]
  }
}
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
	<i class="fa fa-exclamation-triangle"></i> <b>Note:</b> Where no valid parameters are provided in a request, an OperationOutcome with a severity of error <strong>MUST</strong> to be returned as specified in the <a href="https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html#error-handling"> error handling section</a>.
</div>

Providers **MUST** report unsupported parameters at the least granular level, that is, unsupported part parameters **MUST** only be reported when their top level parameter is supported.

Consumers **MUST** check for the presence of an [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) resource as specified above to check for incomplete data as a result of unsupported parameters. These warnings **MUST** be displayed to users to warn them that information is missing.

The following table gives an overview of which parameters are supported in each version of the GP Connect API:

|Specification version|Parameters|
|---|---|
|1.2.x|includeMedication|
||↳ includePrescriptionIssues|
||↳ medicationSearchFromDate|
||includeAllergies|
||↳ includeResolvedAllergies|
|||
|1.5.x|includeMedication|
||↳ includePrescriptionIssues|
||↳ medicationSearchFromDate|
||includeAllergies|
||↳ includeResolvedAllergies|
||includeConsultations|
||↳ consultationSearchPeriod|
||↳ includeNumberOfMostRecent|
||includeProblems|
||↳ includeStatus|
||↳ includeSignificance|
||includeImmunisations|
||↳ includeNotGiven|
||↳ includeStatus|
||includeUncategorisedData|
||↳ uncategorisedDataSearchPeriod|
||includeInvestigations|
||↳ investigationSearchPeriod|
||includeReferrals|
||↳ referralSearchPeriod|
||includeDiaryEntries|
||↳ diaryEntriesSearchDate|
|||
|1.6.2+|includeMedication|
||↳ includePrescriptionIssues|
||↳ medicationSearchFromDate|
||includeAllergies|
||↳ includeResolvedAllergies|
||includeConsultations|
||↳ consultationSearchPeriod|
||↳ includeNumberOfMostRecent|
||includeProblems|
||↳ includeStatus|
||includeImmunisations|
||↳ includeNotGiven|
||↳ includeStatus|
||includeUncategorisedData|
||↳ uncategorisedDataSearchPeriod|
||includeInvestigations|
||↳ investigationSearchPeriod|
||includeReferrals|
||↳ referralSearchPeriod|
||includeDiaryEntries|
||↳ diaryEntriesSearchDate|

Consumers **MAY** determine programmatically which parameters have been implemented by the provider using the following process:

- [Get the FHIR® capability statement](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_get_the_fhir_capability_statement.html) from the provider’s Access Record Structured FHIR server
- Locate the value in `CapabilityStatement.operation[name=’gpc.getstructuredrecord’].definition.reference`, this will be a reference to an `OperationDefinition`
- Perform a HTTP GET to the value that was retrieved in the previous step
- The parameters that are supported by the provider will be listed in `OperationDefinition.parameters`

To illustrate how forwards compatibility works, the following example has been included:

- {{pagelink:Home/Examples/Compatibility-support-examples}}

#### Backwards compatibility

Backwards compatibility is the scenario where a consumer requests a lower version of the API than the provider supports. The GP Connect APIs have been developed to be backwards compatible by following the [rules for backwards compatibility](https://www.hl7.org/fhir/STU3/versions.html#b-compat) that are defined in the FHIR® specification.

Consumers are required to ignore unexpected elements and process data that they understand. They **MUST** alert users to the fact that some information couldn’t be displayed as it isn’t supported.