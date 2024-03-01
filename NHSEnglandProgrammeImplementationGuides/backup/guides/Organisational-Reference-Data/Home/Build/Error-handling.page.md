## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fas fa-exclamation-triangle"></i><b> Important:</b> This page is under development by NHS England</div>

This page is used to describe how errors are handled.

## Errors

The ODS FHIR R4 API will return a {{pagelink:Home/FHIR-Assets/Profiles/UKCore-OperationOutcome.page.md}} when an API call is unsuccessful. The below table provides expected errors / validation failures.

E.g. 
- {{pagelink:Home/Build/Examples/Example-Invalid-ID.page.md}}
- {{pagelink:Home/Build/Examples/Example-Access-Denied.page.md}}

<br>

## Search interaction
| HTTP code         | issue-severity                      | issue-type | details.code / display | details.diagnostics
| ----------- | ------------------------  |------------------------ |------------------------ |------------------------ |
|400 | error | invalid | HAPI 1234 | Invalid NHS number
|400 | error | invalid | HAPI 1234 | Missing or invalid head parameter
|403 | error | forbidden | HAPI 1234 | The sender or receiver's ASID is not authorised for this interaction
|404 | error | not found | HAPI 1234 | The sender or receiver's ASID is not authorised for this interaction