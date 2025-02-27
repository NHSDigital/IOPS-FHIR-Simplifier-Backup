# {{page-title}}

Refer to the [UK Core](https://simplifier.net/guide/UKCoreVersionHistory/Home) standard.

<!--
In the event of a RESTful interaction or operation failure, an `OperationOutcome` resource is used to convey specific detailed processable error information back to the client as part of the HTTP response.

National FHIR APIs delivered by NHS Digital will use a profiled version of this resource; [NHSDigital-OperationOutcome](https://simplifier.net/guide/nhsdigital/NHSDigital-OperationOutcome-duplicate-2). Local implementations should consider using this resource as it contains a comprehsnive value-set of error codes and would give consistancy between local and national API error handling.

In addition to the mandatory elements, the `OperationOutcome` should contain details of the error code in the `OperationOutcome.issue.details.coding.code` and `OperationOutcome.issue.details.coding.display` fields. 

The `OperationOutcome` should provide additional diagnostic details of the error in the `OperationOutcome.diagnostics` property where such details securely provide additional error context for consumer applications. Patient identifiable data should not be included within this property.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The sections below provide guidance on the error details to be returned in a number of key scenarios.
</div>
-->
---

<!--
## Malfotmed request errors

When the server cannot or will not process a request due to an apparent client error then the following `BAD_REQUEST` error **MUST** be used to return debug details.

<table data-responsive>
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>400</code></td>
            <td>invalid</td>
            <td><code>BAD_REQUEST</code></td>
            <td>Submitted request is malformed / invalid.</td>
        </tr>
    </tbody>
</table>

`BAD_REQUEST` [Spine](https://digital.nhs.uk/services/spine) error codes be used in the following types of scenario:

- JWT claims information is not valid JSON, is null, or has an invalid value
- invalid FHIR resource in JWT claim (for example, a `Patient` resource when `Practitioner` expected)
- malformed JSON or XML content in request body
- an expected header is missing or invalid
- invalid HTTP verb used

### Example: Malformed JSON Web Token in request

For example, if the request contained a null claim within a [JSON Web Token (JWT)](https://jwt.io/), then the following error details would be returned:

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
     "issue": [
        {
            "severity": "error",
            "code": "invalid",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "BAD_REQUEST",
                        "display": "Bad request"
                    }
                ]
            },
            "diagnostics": "Malformed JWT"
        }
    ]
}
```
-->
<!--
## Resource validation errors

Where FHIR resource validation issues arise during processing of consumer requests, provider systems **MUST** utilise one the following error details:

<table data-responsive">
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>INVALID_RESOURCE</code></td>
            <td>Submitted resource is not valid.</td>
        </tr>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>INVALID_PARAMETER</code></td>
            <td>Submitted parameter is not valid.</td>
        </tr>
        <tr>
            <td><code>422</code></td>
            <td>invalid</td>
            <td><code>REFERENCE_NOT_FOUND</code></td>
            <td>Referenced resource not found.</td>
        </tr>
    </tbody>
</table>

Detailed diagnostic information **MUST** be supplied when erroring on the codes above.

`INVALID_PARAMATER` would be used in the following, or similar, scenarios:

- An invalid date / time value specified in a custom operation parameter.


`INVALID_RESOURCE` would be used in situations such as the following:

- The resource failed structural validation
- A resource failed to be procesed because of a FHIR constraint, or other rule application, where the error is not already covered by other error codes


`REFERENCE_NOT_FOUND` describes a scenario where a consumer `POST`s a FHIR resource which contains a FHIR reference that cannot be found.

### Example: Reference not found

For example, if a `MedicationRequest` referenced a `Practitioner` resource that could not be found or resolved by the server. The following error details would be returned:

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "invalid",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "REFERENCE_NOT_FOUND",
                        "display": "FHIR reference not found"
                    }
                ]
            },
            "diagnostics": "Referenced Practitioner resource not found"
        }
    ]
}
```
-->
<!--
## Duplicate errors

When responding to consumer API requests, provider systems **MUST** return one of the following `OperationOutcome` details when a resource could not be created or updated because it would cause a duplicate in the provider system:

<table data-responsive>
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>409</code></td>
            <td>duplicate</td>
            <td><code>DUPLICATE_REJECTED</code></td>
            <td>Create would lead to creation of a duplicate resource</td>
        </tr>
    </tbody>
</table>

For example, if the ePMA system attempted to send a `MedicationRequest` that is already an active record on the pharmacy system the error details would be returned:

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "duplicate",
            "details": {
                "coding": [
                {
                    "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                    "code": "DUPLICATE_REJECTED",
                    "display": "Create would lead to creation of duplicate resource"
                }
            ]
        },
        "diagnostics": "MedicationRequest record already exists with that logical identifier"
    }
  ]
}
```
-->
<!--
## Security validation errors

When a client system does not present correct security parameters, provider systems **MUST** return one of the following `OperationOutcome` details:

<table data-responsive>
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>403</code></td>
            <td>forbidden</td>
            <td><code>ACCESS_DENIED</code></td>
            <td>Access denied</td>
        </tr>
    </tbody>
</table>

### Example: Access denied

In this scenario as resource has attempted to be accessed which the requesting user is not authoriused to view.

The JSON below represents an example response that could be returned.

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
    {
        "severity": "error",
        "code": "forbidden",
        "details": {
            "coding": [
                {
                    "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                    "code": "ACCESS_DENIED",
                    "display": "Access denied"
                }
            ]
        },
        "diagnostics": "Invalid authorisation token."
    }
  ]
}
```
-->
<!--
## Identity validation errors

Provider systems **MUST** respond by returning one of the following `OperationOutcome` error codes where FHIR resource identity error scenarios are encountered:

<table data-responsive>
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>400</code></td>
            <td>value</td>
            <td><code>INVALID_IDENTIFIER_SYSTEM</code></td>
            <td>Invalid identifier system</td>
        </tr>
        <tr>
            <td><code>400</code></td>
            <td>value</td>
            <td><code>INVALID_IDENTIFIER_VALUE</code></td>
            <td>Invalid identifier value</td>
        </tr>
        <tr>
            <td><code>400</code></td>
            <td>value</td>
            <td><code>INVALID_NHS_NUMBER</code></td>
            <td>NHS number invalid</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>ORGANISATION_NOT_FOUND</code></td>
            <td>Organisation record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>PATIENT_NOT_FOUND</code></td>
            <td>Patient record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>PRACTITIONER_NOT_FOUND</code></td>
            <td>Practitioner record not found</td>
        </tr>
        <tr>
            <td><code>404</code></td>
            <td>not-found</td>
            <td><code>NO_RECORD_FOUND</code></td>
            <td>No record found</td>
        </tr>
    </tbody>
</table>

### Example: An invalid NHS Number was supplied

In this scenario an invalid NHS number value was supplied. 

The JSON below represents an example response that could be returned.

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "value",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "INVALID_NHS_NUMBER",
                        "display": "Invalid NHS number"
                    }
                ]
            }
        }
    ]
}
```

### Example: The patient could not be found

In this scenario a valid NHS number value was supplied; however, a local record did not exist for the patient in question.

The JSON below represents an example response that could be returned.

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "not-found",
            "details": {
                "coding": [
                    {
                        "system": "https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1",
                        "code": "PATIENT_NOT_FOUND",
                        "display": "Patient not found"
                    }
            ]
        }
    }
  ]
}
```
-->
<!--
## Internal server errors

When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the `NOT_IMPLEMENTED` Spine error code MUST be used.

<table data-resonsive>
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>501</code></td>
            <td>not-supported</td>
            <td><code>NOT_IMPLEMENTED</code></td>
            <td>FHIR resource or operation not implemented at server.</td>
        </tr>
    </tbody>
</table>

When the error is unexpected and the server can’t be more specific on the exact nature of the problem then the `INTERNAL_SERVER_ERROR` Spine error code **MUST** be used, and diagnostics **MUST** be included to provide detail of the error.

<table class="table">
    <thead>
        <tr>
            <th>HTTP code</th>
            <th>Issue type</th>
            <th>Error code</th>
            <th>Error message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>500</code></td>
            <td>processing</td>
            <td><code>INTERNAL_SERVER_ERROR</code></td>
            <td>Unexpected internal server error.</td>
        </tr>
    </tbody>
</table>

### Example: Unexpected exception

For example, if an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:

```json
{
    "resourceType": "OperationOutcome",
    "meta": {
        "profile": [
            "https://fhir.nhs.uk/StructureDefinition/NHSDigital-OperationOutcome"
        ]
    },
    "issue": [
        {
            "severity": "error",
            "code": "exception",
            "details": {
                "coding": [
                    {
                        "system": "https://simplifier.net/guide/NHSDigital/NHSDigital-OperationOutcome-Codes",
                        "code": "INTERNAL_SERVER_ERROR",
                        "display": "Internal server error"
                    }
                ]
            },
            "diagnostics": "Any further internal debug details i.e. stack trace details etc."
        }
  ]
}
```
-->