## Scenario

This example is based on the following Pathology scenario

**Description**

Michael Davies, a 58 year old man, attends an appointment at an oncology outpatient clinic at Lingfield Royal Infirmary.  The consultant, Dr Ibrahim Khan, gives Michael a blood test form for a prostate-specific antigen (PSA) test and asks him to attend the hospital’s phlebotomy clinic.

On the same day, Michael attends the phlebotomy clinic and hands in the blood test form.  A blood sample is taken by one of the clinic phlebotomists, Juan Garcia, and sent to the laboratory based in the hospital.

The sample is received by the laboratory, checked and matched with the test request.  The details are recorded on the Laboratory Information Management System (LIMS). 

The test is performed, and the results are authorised for release.  The following test results (and reference ranges) are sent electronically from the LIMS to the hospital’s Electronic Patient Record (EPR) system and the GP system at Michael’s GP surgery:

|Test|Result|Reference Range|
|----|-------|----|
|Prostate Specific Antigen|5.9 ug/L|(0 to 4)|

## Named participants ##

- Patient: Michael Davies – FHIR Resource: {{pagelink:Patient}}
- Requesting HCP: Dr Ibrahim Khan – FHIR Resource: {{pagelink:Practitioner}}

## Named Organisations ##

- Requesting Organisation: Lingfield Royal Infirmary (Oncology) – FHIR Resource: {{pagelink:Organization}}
- Specimen Collecting Organisation: Lingfield Royal Infirmary (Oncology) – FHIR Resource: {{pagelink:Organization}}
- Performing Organisation: Lingfield Royal Infirmary (Blood Sciences) – FHIR Resource: {{pagelink:Organization}}


## Required Tests ##

- PSA – FHIR Resource: {{pagelink:ServiceRequest}}

|Code|Display|
|----|-------|
|63476009|Prostate specific antigen measurement|


## Specimen(s) ##

- Blood – FHIR Resource: {{pagelink:Specimen}}

|Code|Display|
|----|-------|
|119361006|Plasma specimen|

## Test Report ##

- FHIR Resource: {{pagelink:DiagnosticReport}}

|Code|Display|
|----|-------|
|721981007|Diagnostic studies report|

## Test Results ##

- FHIR Resource: {{pagelink:Observation}}

|Code|Display|Value|Unit|
|----|-------|-----|----|
|1107801000000104|Prostate specific antigen mass concentration in plasma|5.9|ug/L|
