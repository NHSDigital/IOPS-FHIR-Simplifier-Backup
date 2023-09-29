## {{page-title}}


This page is used to describe how errors are handled.

## Errors

The CP-IS FHIR R4 API will return a {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-OperationOutcome.page.md}} when an API call is unsuccessful. The below table provides expected errors / validation failures.

E.g. {{pagelink:Home/Examples/Example---Invalid-NHS-Number.page.md}}

<br>

## Search interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | INVALID_SEARCH_DATA | Invalid NHS number
|400 | error | invalid | PRECONDITION_FAILED | Missing or invalid head parameter
|403 | error| forbidden | ACCESS_DENIED | Access has been denied to process this request 

<br>

