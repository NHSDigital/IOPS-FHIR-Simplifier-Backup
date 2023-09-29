# Pharmacy to direct care API model - FHIR STU3 (GP Connect Representation – Pharmacy Data Set Mandatory fields) - Encounter1

The table represents the FHIR field mapping for flowing and presenting medication patient data from community pharmacy to the GP service.  The ‘Not Present’ text highlights where there is no representative field for FHIR translation and will require further investigation.  However, these fields are required community pharmacy fields, so can be marked as null values, when presenting to the GP service

|Community Pharmacy|Conformance|Encounter1|Use/Conformance|
|:-----------------|:----------|:---------|:--------------|
|Person demographics|M|||
|Person name|M|Participant/Individual|1..*|
|Person full name|M|Participant/Individual|1..*|
|Date of birth|M|Not Present|
|Person's address|M|Not Present|
|Address line 1|M|Not Present|
|GP practice|M|||
|GP practice identifier|M|Identifier|1..*|
|Reason for referral|M|Reason|0..*|
|Contacts with professionals|M|
|Contacts with professionals record entry|M|Participants|1..*|
|Date and time of contact|M|Period/Start|1..1|
|Organisation name|M|serviceProvider|0..1|
|Clinician name|M|Identifier|1..*|
|Clinical Summary|M|diagnosis|0..*|
|Clinical narrative|M|Reason/coding/text|0..1|
|Causative agent|M|Diagnosis/condition|1..1|
|Medication name|M|Diagnosis/condition|1..1|
|Quantity supplied|M|Identifier/value|1..1|
|Matters identified during discussion|M|Diagnosis/condition|1..1|

----

# Mapping to GP Connect Data Model - FHIR STU3 Representation – Medication

The table below shows the FHIR field mapping for flowing and presenting medication patient data from community pharmacy to the GP service.  The ‘Not Present’ text highlights where there is no representative field for FHIR translation and will require further investigation.  However, these fields are required community pharmacy fields, so can be marked as null values, when presenting to the GP service

|Name|Conformance|Medication1|Use/Conformance|
|:-----------------|:----------|:---------|:--------------|
|Medications and medical devices|R
|Medication item entry|R|Code/display|0…1|
|Medication item cluster|R|Code/coding/code|1…1|
|Date|R|Not Present|
|Medication name|M|manufacturer|0..1|
|Coded value|R|form/coding/display|0..1|
|Free text|R|form/text|0..1|
|Form|R|form/coding/display|1..1|
|Coded value|R|form/coding/code|1..1|
|Free text|R|form/text|0..1|
|Quantity supplied|M|ingredient/item/amount|0..1|
|Value|R|ingredient/item/amount|0..1|
|Unit of measure|R|ingredient/item/amount|0..1|
|Route|R|Not Present|
|Coded value|R|Not Present|
|Free text|R|form/text|0..1|
|Site|R|Not Present|
|Coded value|R|Code/Coding/code|1..1|
|Free text|R|Code/display|0…1|
|Supply type|R|package/content/item|1..1|
|Batch number|R|batch|0..*|
|Coded value|R|package/batch/lotNumber|0..1|
|Free text|R|package/batch/lotNumber|0..1|
|Structured dose direction cluster|R|Not Present|
|Structured dose amount|R|Not Present|
|Structured dose timing|R|Not Present|
|Dose direction duration|R|Not Present
|Dose directions description|R|Not Present|
|Additional instructions|R|Not Present
|Matters identified during discussion|M|form/text|0..1|
|Course details cluster|R|form/text|0..1
|Indication|R|form/text|0..1|
|No supply reason|TBC|form/text|0..1|

----

# Mapping to GP Connect Data Model - FHIR STU3 Representation – Observations

The table below shows the FHIR field mapping for flowing and presenting Observations patient data from community pharmacy to the GP service.  When representing the community pharmacy data, there are 2 parts, the observations and examination part and the relevant observation for the type of observation is being observed.  The table below provides an indication for the mappings and representation.

|Name|Conformance|Observation|Use/Conformance|
|:-----------------|:----------|:---------|:--------------|
|Observations|R|Value/valueString|Not Defined|
|Examination findings record entry|R|Value/valueString|Not Defined|
|Date|R|Effective/EffectiveDateTime|Not Defined|
|Observations|R|Identifier / value|1..1|
|Height/length|R|Code/subject|1..1|
|Coded value|R|Value/valueQuantity|CareConnect-Quantitiy-1
|Value|R|Identifier / value|1..1
|Units of measure|R|Value/valueString|Not Defined
|Weight|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|BMI|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Blood Pressure|R|Identifier / value|1..1|
|Systolic blood pressure|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Coded value|R|Identifier/use|0..1
|Value|R|Identifier/use|0..1
|Units of measure|R|Value/valueString|Not Defined
|Site|R|Value/valueString|CareConnect-Quantitiy-1
|Coded value|R|Idenifier / value|1..1
|Free text|R|Value/valueString|Not Defined
|Diastolic blood pressure|R|Code/subject|1..1
|Coded value|R|Identifier/use|0..1
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1
|Units of measure|R|Value/valueString|Not Defined
|Site|R|Code/subject|1..1|
|Coded value|R|Identifier/use|0..1|
|Free text|R|Value/valueQuantity|CareConnect-Quantitiy-1
|Heart Rate|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Temperature|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Oxygen|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Pain Score|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Level of Consciousness|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Respiratory Rate|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|Air or Oxygen|R|Identifier / value|1..1|
|Coded value|R|Identifier/use|0..1|
|Value|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Units of measure|R|Value/valueString|Not Defined|
|National early warning score (NEWS2)|R|Identifier / value|1..1|
|Coded value total score|R|Identifier/use|0..1|
|Value for total score|R|Value/valueQuantity|CareConnect-Quantitiy-1|
|Coded value subscore|R|Value/valueString|CareConnect-Quantitiy-1|
|Subscore|R|Value/valueString|CareConnect-Quantitiy-1|

----





