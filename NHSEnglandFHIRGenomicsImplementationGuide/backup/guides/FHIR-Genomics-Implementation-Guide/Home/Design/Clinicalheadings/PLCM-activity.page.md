## {{page-title}}

### Purpose
For PLCM activity submissions. 
This section is pending review, supporting PLCM activity reporting is not expected as part of the Genomic Order Management Alpha.

### Notes
Derived from existing fields used for clinical/operational purposes in the test order/response.



### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|PLCM activity - NGIS referral identifier|ServiceRequest.identifier|ORC-3|NGIS referral identifier|
|PLCM activity - Financial month|Derived from ServiceRequest.authoredOn|Derived from ORC-9|The month in which the PLCM activity occurred.|
|PLCM activity - Financial year|Derived from ServiceRequest.authoredOn|Derived from ORC-9|The financial year in which the PLCM activity occurred.|
|PLCM activity - Date and time dataset created|Derived from DiagnosticReport.effectiveDateTime based on ServiceRequest|Derived from OBR-7 in the ORL response message for the activity based on the OML request|The date and time a file was created prior to submission to Data Landing Portal (DLP).|
|PLCM activity - Activity start date and time|Derived from Task.executionPeriod.start for activity based on ServiceRequest|Derived from TQ1-7 in the ORL response message for the activity based on the OML request|The date and time of the defined PLCM activity start date for the relevant activity.|
|PLCM activity - Activity end date and time|Derived from Task.executionPeriod.end for activity based on ServiceRequest|Derived from TQ1-8 in the ORL response message for the activity based on the OML request|The date and time of the defined PLCM activity end date for the relevant activity.|
|PLCM activity - Patient age at activity date|Derived from the difference between Patient.birthDate and Task.executionPeriod.start for the relevant activity|Derived from the difference between PID-7 and TQ1-7 for the relevant activity|Age of the patient at the date a PLCM activity is undertaken.|
|PLCM activity - ODS code of organisation submitting to PLCM|Task.owner if pulled directly from broker system|OBR-32.7 if sourced from principle results interpreter|ODS code of the organisation submitting the PLCM data specification.|
|PLCM activity - ODS code of organisation commissioned to deliver requested test|ServiceRequest.performer if pulled directly from broker system|PRD-7 where PRD-1=RT|ODS code of the organisation commissioned by NHS England to deliver the service.|
|PLCM activity - ODS code of organisation delivering requested test|Task.owner|OBX-32.10|ODS code of the organisation delivering the service.|
|PLCM activity - ODS code of the laboratory site delivering requested test|Task.owner( PractitionerRole.healthcareService( HealthcareService.identifier ) )|AFF-2.10 associated with performing organization|ODS code of the site on which the laboratory delivering the service is based.|
|PLCM activity - ODS code of commissioning region|Organization.partOf|N/A - not in scope for HL7v2|ODS code of the commissioning region.|
|PLCM activity - Commissioned service category code|Derived from ServiceRequest.requester( PractitionerRole.healthcareService )|Derived from STF-8 for requester|PLCM category code for the service commissioning the test request.|
|PLCM activity - Service code|Derived from ServiceRequest.code|Derived from OBR-4|PLCM Service code to confirm if the test request is for a specialised service.|
|PLCM activity - Point of delivery code|Derived from ServiceRequest.code|Derived from OBR-4|PLCM point of delivery code.|
|PLCM activity - Local point of delivery code|Derived from ServiceRequest.code|Derived from OBR-4|PLCM local point of delivery code.|
|PLCM activity - Turnaround time (calendar days)|Derived from difference between ServiceRequest.authoredOn and resulting DiagnosticReport.effectiveDateTime|Derived from difference between ORC-9 and OBR-7 for resulting report|To be populated with the actual turnaround time for the activity expressed in calendar days.|
|PLCM activity - Turnaround time standard (calendar days)|N/A fixed dependent on test type|N/A fixed dependent on test type|To be populated with the relevant turnaround time standard for the activity expressed in calendar days at TESTREPORT activity stage, else blank.|
|PLCM activity - Compliant with turnaround time standard (calendar days)|N/A derived from fixed standard and current turnaround time|N/A derived from fixed standard and current turnaround time|To be populated with Y=Yes, N=No at TESTREPORT activity stage, else blank.|
|PLCM activity - Test method code|Derived from ServiceRequest.code|Derived from OBR-4|PLCM test method code.|
|PLCM activity - Sample plating quality control|Implied though completion of SpecimenProcessing Task|Implied through status recorded in ORC-25 indicating plating quality control had passed|Confirmation if the sample plating has passed quality control.|
|PLCM activity - Sample plating quality control fail code|Task.statusReason for SpecimenProcessing Task|ORC-25|Sample plating, quality control, fail code.|
|PLCM activity - Sample volume|Specimen.collection.quantity|SPM-12|Sample volume in (µl).|
|PLCM activity - DNA concentration|Observation attached to Specimen with code 13925004 and appropriate UCUM unit|OBR attached to SPM segment with code 13925004 and appropriate UCUM unit|DNA concentration in (ng/ul).|
|PLCM activity - DNA quantification|Observation attached to Specimen with code 13925004 and appropriate UCUM unit|OBR attached to SPM segment with code 13925004 and appropriate UCUM unit|DNA quantification in (µg).|
|PLCM activity - Sample category code|Derived from Specimen.type|Derived from SPM-4|PLCM sample category code.|
|PLCM activity - Quality score for sequencing|N/A Derived from DNA concentration/quantification|N/A Derived from DNA concentration/quantification|Quality score for sequencing.|
|PLCM activity - Local report identifier|DiagnosticReport.identifier|OBR-3 for report|Identifier for the issued report|
|PLCM activity - Test outcome code (Many)|DiagnosticReport.result( Observation.code )|OBX-3 elements for resulting report|PLCM test outcome codes.|
