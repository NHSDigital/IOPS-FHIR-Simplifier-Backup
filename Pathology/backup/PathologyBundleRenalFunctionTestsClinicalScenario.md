## Clinical Scenario

This example is based on the following Pathology scenario

**Description**

Lisa Stanner, a 60 year old woman, attends Manor GP Practice for monitoring her hypertension.  Lisa’s GP, Dr Jane Green, requests renal function tests (electrolytes and creatinine profile).  The request is sent electronically using an order comms system (accessed via the GP practice system) to the pathology laboratory based in the local hospital, Midtown District Hospital.

Dr Green books an appointment with the practice nurse, Alice Jones.  Lisa attends the appointment the following day where the blood sample is taken and sent to the laboratory.

The sample is received by the laboratory, checked and matched with the test request.  The details are recorded on the Laboratory Information Management System (LIMS).

The tests are performed, and the results are authorised for release.  The following test results (and reference ranges) are sent electronically from the LIMS to the GP practice system:


**Electrolytes and Creatinine Profile**

|Type|Units|Range|
|--|--|
|Sodium|142 mmol/L|(133 to 146)|
|Potassium|4.8 mmol/L|(3.5 to 5.3)|
|Chloride|105 mmol/L|(95 to 108)|
|Creatinine|64 umol/L|(48 to 128)|
|EGFR|87 mL/min/1.73m<sup>2</sup>||
|Comments|The EGFR quoted above must be multiplied by 1.2 if the patient is of Afro-Caribbean origin.|

## Named participants ##

- Patient: Patient: Lisa Stanner – FHIR Resource: {{pagelink:Patient}}
- Requesting HCP: Dr Jane Green – FHIR Resource:  {{pagelink:Practitioner}}

## Named Organisations ##

- Requesting Organisation: Manor GP Practice – FHIR Resource:  {{pagelink:Organization}}
- Specimen Collecting Organisation: Manor GP Practice – FHIR Resource:  {{pagelink:Organization}}
- Performing Organisation: Midtown District Hospital (Blood Sciences) – FHIR Resource:  {{pagelink:Organization}}

## Required Tests ##

- Electrolytes and creatinine – FHIR Resource:  {{pagelink:ServiceRequest}}

|Code|Display|
||
|54610007|Kidney panel|

## Specimen(s) ##

- Blood – FHIR Resource: {{pagelink:Specimen}}

|Code|Display|
||
|119361006|Plasma specimen|

## Test Report ##

- FHIR Resource: {{pagelink:DiagnosticReport}}

|Code|Display|
||
|721981007|Diagnostic studies report|

## Test Results ##

- FHIR Resource: {{pagelink:Observation}}

|Code|Display|Value|Unit|
||||
|1015971000000100|Renal function tests|-|-|
|1107871000000107|Sodium substance concentration in serum|142|mmol/L|
|1107761000000109|Potassium substance concentration in serum|4.8|mmol/L|
|1106511000000102|Chloride substance concentration in serum|105|mmol/L|
|1107001000000108|Creatinine substance concentration in serum|64|umol/L|
|1107411000000104|Estimated glomerular filtration rate by laboratory calculation|87|mL/min/1.73m<sup>2</sup>|