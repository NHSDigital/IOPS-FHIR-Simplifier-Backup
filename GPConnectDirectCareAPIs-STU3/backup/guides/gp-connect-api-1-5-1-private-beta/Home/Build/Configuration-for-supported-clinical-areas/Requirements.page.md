## {{page-title}}

### Clinical areas

The configuration of the Provider system **MAY** allow for clinical areas to be switched on or off for all sites without requiring a release. This **MAY** be achieved using a single configuration item or action.

For example, in the case of a clinical safety incident with a clinical area where a provider would be required to turn off the clinical area across their entire estate. Where information for a clinical area isn’t returned, provider systems **MUST** return a warning for each clinical area that isn’t supported according to the rules below.

The following clinical areas can be configured to be on or off:

- Medications
- Allergies
- Consultations
- Problems
- Uncategorised data
- Immunisations
- Investigations
- Referrals
- Diary entries
- Documents

The Documents item controls whether `DocumentReference` resources are returned as part of the structured response, this configuration item works independently of the Access Documents capability [enablement](#Enablement).

### Site switch

In addition to the above, the configuration of the Provider system **MUST** allow for the availability of a clinical area to be switched on or off at one or more sites without requiring a release. For example, in the scenario where there was a data quality issue with a clinical area at a single site. Where information for a clinical area isn’t returned, provider systems **MUST** return a warning for each clinical area that isn’t available according to the rules below.

### Consumer systems

Consumer systems **MUST** be able to handle the unavailability of clinical areas and warn users that information hasn’t been returned.

### Populating a warning

In the above scenarios, providers **MUST** respond in the following way:

- return a `200` **OK** HTTP status code to indicate successful retrieval of a patient’s structured record
- include FHIR® resources for clinical areas that are switched on
- as part of the returned bundle, include a single [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) with an `issue` for each clinical area that is disabled, that is, any disabled clinical area that would have been included either in response to a query parameter or linked to from requested clinical information, where:
    - `issue.code` = `not-supported`
    - `issue.severity` = `warning`
    - `issue.details.coding.system` = `https://fhir.nhs.uk/STU3/CodeSystem/Spine-ErrorOrWarningCode-1`
    - `issue.details.coding.code` = `NOT_IMPLEMENTED`
    - `issue.details.coding.display` = `Not implemented`
- for each disabled clinical area the following **MUST** be supplied:
    
    - `issue.details.text` = `<parameter-name>` has been disabled
    - `issue.diagnostics` = `<parameter-name>`
    - Where documents have been switched off ‘DocumentReferences’ **MUST** be returned in place of `<parameter-name>`.
    - Providers **MAY** choose to return an empty [List](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current) resource as well as the [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current). This **MAY** be populated with limited information such as `warningCode` or `emptyReason`.
    
    The example shows a fully populated [`OperationOutcome`](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-OperationOutcome-1?version=current) for a request where the `includeProblems` clinical area has been turned off:
    

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
          "text": "includeProblems has been disabled"
        },
        "diagnostics": "includeProblems"
      }
    ]
  }
}
```

### Populating references to clinical areas that aren’t available

Where clinical areas are unavailable, references to them will need to be populated with a warning that the information is unavailable. However, if the clinical item that is unavailable is also marked as confidential, then the response should be as per the {{pagelink:Home/Build/Using-lists-to-return-data/Warning-codes.page.md}} (Confidential items).

Where a clinical area has been turned off, it will create a section.section.entry (or section.entry) entry with the:

- `List.entry.item.display` set to “[Clinical area] items have been disabled.”
    
    Where [Clinical area] identifies the type of the clinical item that isn’t available.
    
    The example below shows references to two items, one for an observation and another for referrals that have been disabled in the provider system:
    

```json
{
  "item": {
    "reference": "Observation/6734572634"
  }
},
{
  "item": {
    "display": "Referral items have been disabled"
  }
}
```