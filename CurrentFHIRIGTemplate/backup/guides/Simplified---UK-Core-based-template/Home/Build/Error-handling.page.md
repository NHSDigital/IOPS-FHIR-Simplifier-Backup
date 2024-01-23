## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

This page is used to describe how errors are handled.

## Errors

The FGM-IS FHIR R4 API will return a {{pagelink:Home/FHIRAssets/Profiles/UKCore-OperationOutcome.page.md}} when an API call is unsuccessful. The below table provides expected errors / validation failures.

E.g. {{pagelink:Home/Examples/Example---Invalid-NHS-Number.page.md}}

<br>

## Search interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | INVALID_SEARCH_DATA | Invalid NHS number
|400 | error | invalid | PRECONDITION_FAILED | Missing or invalid head parameter
|403 | error| forbidden | ACCESS_DENIED | The sender or receiver's ASID is not authorised for this interaction

<br>

## Add interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | INVALID_VALUE | Invalid NHS number
|400 | error | invalid | UNSUPPORTED_VALUE | Code must be 902961000000107
|400 | error | invalid | UNSUPPORTED_VALUE | Status must be active on this interaction
|400 | error | invalid | VALIDATION_ERROR | Patient is over 18
|400 | error | invalid | VALIDATION_ERROR | Patient gender must be female, unknown or indeterminate 
|400 | error | invalid | VALIDATION_ERROR | Flag value was already set
|400 | error | invalid | VALIDATION_ERROR | Removal reason not allowed on this interaction
|400 | error | invalid | PRECONDITION_FAILED | Missing or invalid head parameter
|403 | error | forbidden | ACCESS_DENIED | The sender or receiver's ASID is not authorised for this interaction

<br>

## Remove interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | RESOURCE_NOT_FOUND | Resource not found
|400 | error | invalid | INVALID_VALUE | ID specified in the URL does not match the ID specified in the resource
|400 | error | invalid | VALIDATION_ERROR | Removal reason must be supplied
|400 | error | invalid | PRECONDITION_FAILED | Missing or invalid head parameter
|403 | error | forbidden |ACCESS_DENIED | The sender or receiver's ASID is not authorised for this interaction