## Coded Entries for COVID-19 Mappings

There are 5 COVID SNOMED CT terms that act as triggers in the Summary Care Record Application (SCRa) to trigger the displaying of warning boxes.These codes are documented on the [Coronavirus (COVID-19) message in SCR](https://digital.nhs.uk/services/summary-care-records-scr/coronavirus-covid-19-message-in-scr#snomed-ct-terms-that-will-cause-the-yellow-message-box-to-display) page on the NHS Digital website.

The 5 codes are 

|Concept|Preferred term|SCR Section|
|--
|1240751000000100|COVID\-19|Diagnoses|
|1300721000000109|COVID\-19 confirmed by laboratory test|Diagnoses|
|1240581000000104|SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive|Clinical Observations and Findings|
|1300731000000106|COVID-19 confirmed using clinical diagnostic criteria|Diagnoses|
|1240761000000102|Suspected COVID-19|Diagnoses|

## Generic Mapping

Within the HL7v3 model, all coded entries originate from the same link class (pertinentInformation2). For each of the SCR Section types will have the same XML to cover the HL7v3 model from the link class pertinentInformation2 through to the component link off the relevant CMET (Diagnosis or Investigation Results OR Clinical Observations and Findings)

The only data item that varies between the CMET choice is the value of pertinentInformation2\pertinentCREType\code - which holds the relevant CREType code. The rest of the values used in the HL7v3 model are all fixed values. None of these values have any FHIR mapping - other than the CREType selected for the HL7v3 will indicate which FHIR resource should be used.

### pertinentInformation2

**Note:** pertinentInformation2 repeats for each type of CREType

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|pertinentInformation2@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "PERT"|
||||
|**Item**|**@inversionInd**|
|**HL7v3**|pertinentInformation2@inversionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
||||
|**Item**|**@contextConductionInd**|
|**HL7v3**|pertinentInformation2@contextConductionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "true"|
||||
|**Item**|**@negationInd**|
|**HL7v3**|pertinentInformation2@negationInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
||||
|**Item**|**templateId@root**|
|**HL7v3**|pertinentInformation2@templateId@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"|
||||
|**Item**|**templateId@extension**|
|**HL7v3**|pertinentInformation2\templateId@extension|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CSAB_RM-NPfITUK10.pertinentInformation1"|
||||
|**Item**|**seperatableInd@value**|
|**HL7v3**|pertinentInformation2\seperatableInd@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "true"|

### HL7v3 example
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
    <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
    <seperatableInd value="true"/>
```

### pertinentCREType

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|pertinentCREType@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CATEGORY"|
||||
|**Item**|**@moodCode**|
|**HL7v3**|pertinentCREType@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "EVN"|
||||
|**Item**|**code@code**|
|**HL7v3**|pertinentCREType\code@code|
|**FHIR**|no mapping|
|**Notes**|HL7v3: A code from the CRE SNOMED hierarchy\(<162931000000103\). The values for COVID\-19 will be one of:<br/>163001000000103 \| Diagnoses<br/>163131000000108 \| Clinical observations and findings<br/>163141000000104 \| Investigation results<br/>**Note:** the COVID code(s) sent must appear in the relevant CMET - see below. This will indicate the FHIR resource type to be used.|
||||
|**Item**|**code@codeSystem**|
|**HL7v3**|pertinentCREType\code@codeSystem|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.15"|
||||
|**Item**|**code@displayName**|
|**HL7v3**|pertinentCREType\code@displayName|
|**FHIR**|no mapping|
|**Notes**|HL7v3: The display of the selected code|

### HL7v3 example
```xml
<pertinentCREType classCode="CATEGORY" moodCode="EVN">
    <code code="163001000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Diagnoses"/>
```

### component

**Note:** the component repeats for each instance of a given CREType

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|component@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "COMP"|
||||
|**Item**|**@contextConductionInd**|
|**HL7v3**|component@contextConductionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "true"|
||||
|**Item**|**templateId@root**|
|**HL7v3**|component@templateId@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"|
||||
|**Item**|**templateId@extension**|
|**HL7v3**|component\templateId@extension|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CSAB_RM-NPfITUK10.component"|
||||
|**Item**|**seperatableInd@value**|
|**HL7v3**|component\seperatableInd@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|

### HL7v3 example
```xml
<component typeCode="COMP" contextConductionInd="true">
    <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
    <seperatableInd value="false"/>
```
### HL7v3 example of Generic XML
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
    <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
    <seperatableInd value="true"/>
    <pertinentCREType classCode="CATEGORY" moodCode="EVN">
        <code code="163001000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Diagnoses"/>
        <component typeCode="COMP" contextConductionInd="true">
            <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
            <seperatableInd value="false"/>
```

### XML Overview of Generic XML

<div class="summary-structure-img">
{{render:HL7v3CodedEntry}}
</div>



**The appropriate CMET (SCR Section) is then chosen to carry the data.<br/>- For Diagnoses use A_Diagnosis (UKCT_RM144042UK01)<br/>- For Investigation Results OR Clinical Observations and Findings use A_Finding (UKCT_RM144043UK02)
<br/><br/>Both of these CMETs share the same author classes. The author classes are documented once.**

### Mapping Diagnoses Coded Entries

For the Diagnoses Coded Entries see [Mapping Diagnoses](DiagnosisCodedEntry)

For the Investigation Results and Clinical Observations and Findings see [Mapping Finding](FindingCodedEntry)

For the generic participations see [Mapping Participants](ParticipantCodedEntry)

