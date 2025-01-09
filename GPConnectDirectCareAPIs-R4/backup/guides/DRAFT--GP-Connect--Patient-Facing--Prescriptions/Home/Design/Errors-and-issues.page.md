## {{page-title}}

<table data-responsive>
    <thead>
        <tr>
            <th>Issue</th>
            <th>Mapping</th>
            <th>HTTP Status</th>
            <th>Issue.code</th>
            <th>Issue.severity</th>
            <th>Issue.details.coding.code</th>
            <th>Issue.details.coding.display</th>
            <th>Endpoint?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Not authorised</td>
            <td>ACCESS_DENIED</td>
            <td>401</td>
            <td></td>
            <td>error</td>
            <td>ACCESS_DENIED</td>
            <td></td>
            <td>All</td>
        </tr>
        <tr>
            <td>Prescribed item description does not match code</td>
            <td>CONFLICTING_VALUES</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>CONFLICTING_VALUES</td>
            <td></td>
            <td>Request a repeat prescription</td>
        </tr>
        <tr>
            <td>Prescribed item quantity description does not match code</td>
            <td>CONFLICTING_VALUES</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>CONFLICTING_VALUES</td>
            <td></td>
            <td>Request a repeat prescription</td>
        </tr>
        <tr>
            <td>Mismatched prescribed item to quantity</td>
            <td>CONFLICTING_VALUES</td>
            <td>400</td>
            <td>business-rule</td>
            <td>error</td>
            <td>CONFLICTING_VALUES</td>
            <td></td>
            <td>Request a repeat prescription</td>
        </tr>
        <tr>
            <td>BasedOn reference to previous prescription does not match previous</td>
            <td>CONFLICTING_VALUES</td>
            <td>400</td>
            <td>business-rule</td>
            <td>error</td>
            <td>CONFLICTING_VALUES</td>
            <td></td>
            <td>Get medications relating to a patient</td>
        </tr>
        <tr>
            <td>Duplicate prescription request</td>
            <td>DUPLICATE_REJECTED</td>
            <td>400</td>
            <td>duplicate</td>
            <td>error</td>
            <td>DUPLICATE_REJECTED</td>
            <td></td>
            <td>Request a repeat prescription</td>
        </tr>
        <tr>
            <td>Invalid prescribed item code</td>
            <td>INVALID_CODE_VALUE</td>
            <td>400</td>
            <td>code-invalid</td>
            <td>error</td>
            <td>INVALID_CODE_VALUE</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Invalid prescribed item quantity code</td>
            <td>INVALID_CODE_VALUE</td>
            <td>400</td>
            <td>code-invalid</td>
            <td>error</td>
            <td>INVALID_CODE_VALUE</td>
            <td></td>
        </tr>
        <tr>
            <td>Invalid task ID</td>
            <td>INVALID_IDENTIFIER_VALUE</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_IDENTIFIER_VALUE</td>
            <td></td>
        </tr>
        <tr>
            <td>Invalid patient ID</td>
            <td>INVALID_NHS_NUMBER</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_NHS_NUMBER</td>
            <td></td>
        </tr>
        <tr>
            <td>Invalid date</td>
            <td>INVALID_PARAMETER</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_PARAMETER</td>
            <td></td>
        </tr>
        <tr>
            <td>Attempted cancellation once cancelled or prescribed</td>
            <td>INVALID_REQUEST_STATE</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_REQUEST_STATE</td>
            <td></td>
        </tr>
        <tr>
            <td>BasedOn reference to previous prescription not present</td>
            <td>INVALID_RESOURCE</td>
            <td>400</td>
            <td>required</td>
            <td>error</td>
            <td>INVALID_RESOURCE</td>
            <td></td>
        </tr>
        <tr>
            <td>Invalid prescribed item quantity</td>
            <td>INVALID_VALUE</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_VALUE</td>
            <td></td>
        </tr>
        <tr>
            <td>Note too long</td>
            <td>INVALID_VALUE</td>
            <td>400</td>
            <td>too-long</td>
            <td>error</td>
            <td>INVALID_VALUE</td>
            <td></td>
        </tr>
        <tr>
            <td>Task or request date not in past</td>
            <td>INVALID_VALUE</td>
            <td>400</td>
            <td>value</td>
            <td>error</td>
            <td>INVALID_VALUE</td>
            <td></td>
        </tr>
        <tr>
            <td>Dispensing organisation not found</td>
            <td>ORGANISATION_NOT_FOUND</td>
            <td>404</td>
            <td>not-found</td>
            <td>error</td>
            <td>ORGANISATION_NOT_FOUND</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient not found</td>
            <td>PATIENT_NOT_FOUND</td>
            <td>404</td>
            <td>not-found</td>
            <td>error</td>
            <td>PATIENT_NOT_FOUND</td>
            <td></td>
        </tr>
        <tr>
            <td>Task not found</td>
            <td>RESOURCE_NOT_FOUND</td>
            <td>404</td>
            <td>not-found</td>
            <td>error</td>
            <td>RESOURCE_NOT_FOUND</td>
            <td></td>
            <td>Get requested prescription reorders, Cancel an unactioned repeat prescription request</td>
        </tr>                      
    </tbody>
</table>

#### Operation Outcome Usage
In the event of an error, provider systems **SHALL** respond by providing an `OperationOutcome` profiled to {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-OperationOutcome}}.

#### Example
```json
{
  "resourceType" : "OperationOutcome",
  "issue" : [ {
    "severity" : "error",
    "code" : "value",
    "details" : {
      "coding" : [ {
        "system" : "https://fhir.nhs.uk/R4/CodeSystem/Spine-ErrorOrWarningCode",
        "version" : "1",
        "code" : "MISSING_FIELD",
        "display" : "ResourceType Bundle must contain 'entry' field"
      } ]
    }
  } ]
}
```