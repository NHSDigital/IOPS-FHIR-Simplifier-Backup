## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fas fa-exclamation-triangle"></i><b> Important:</b> This page is under development by NHS England</div>

This page is used to describe how errors are handled.

## Errors

The ODS FHIR R4 API will return a {{pagelink:Home/FHIR-Assets/Profiles/UKCore-OperationOutcome.page.md}} when an API call is unsuccessful. The below table provides expected errors / validation failures.

<br>

## Search interaction

| HTTP code | issue-severity | issue-type | details.code / display | details.diagnostics | Example |
| --------- | -------------- |----------- | ---------------------- | ------------------- | ------- |
|400 | error | invalid | HAPI-1940 | Invalid Date/Time/Quantity format | {{pagelink:Example-Error-Invalid-Format}}
|400 | error | invalid | HAPI-0524 | Unknown Search Parameter  | {{pagelink:Example-Error-Unknown-Search-Parameter}}
|404 | error | not found | HAPI-2001 | Organization not found | {{pagelink:Example-Error-Invalid-ID}}
|405 | error | method not allowed | HAPI-0427 | Organization not found | {{pagelink:Example-Error-Method-Not-Allowed}}
|422 | error | unprocessable | too-costly  | Too many records requested, use _count and _offset | {{pagelink:Example-Error-Too-Costly}}
|422 | error | unprocessable | processing | No declared filter on Codesystem | {{pagelink:Example-Error-No-Declared-Filter}}