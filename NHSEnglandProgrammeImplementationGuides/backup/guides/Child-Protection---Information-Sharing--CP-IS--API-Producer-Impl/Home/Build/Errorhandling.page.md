## {{page-title}}

This page describes how errors are handled.

## Errors

The CP-IS FHIR R4 API will return a {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-OperationOutcome.page.md}} when an API call is unsuccessful. The below table provides expected errors / validation failures.

e.g: <a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-consumer-impl/home/examples/use-case---get-careteam.page.md?version=current#error-case">403 Error Operation Outcome</a>



<br>

## Search interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | INVALID_SEARCH_DATA | Invalid NHS number
|400 | error | invalid | PRECONDITION_FAILED | Missing or invalid head parameter
|403 | error| forbidden | ACCESS_DENIED | Access has been denied to process this request 

<br>
