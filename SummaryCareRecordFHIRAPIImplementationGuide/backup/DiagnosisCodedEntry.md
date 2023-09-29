#### Diagnosis Coded Entry

The Diagnosis Coded Entry covers 4 out of the 5 COVID-19 codes

|Concept|Preferred term|SCR Section|
|--
|1240751000000100|COVID\-19|Diagnoses|
|1300721000000109|COVID\-19 confirmed by laboratory test|Diagnoses|
|1300731000000106|COVID-19 confirmed using clinical diagnostic criteria|Diagnoses|
|1240761000000102|Suspected COVID-19|Diagnoses|

**The Diagnoses HL7v3 CMET will map to a FHIR Condition resource.**

### Diagnoses (excluding participants)

<div class="summary-structure-img">
{{render:Diagnosis}}
</div><br/>


||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "OBS"<br/>FHIR: this has no mapping in FHIR|
|||
|**Item**|**@moodCode**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis@moodCode|
|**FHIR**|no mapping|
|**Notes**|Hl7v3: fixed to "EVN"<br/>FHIR: this has no mapping in FHIR|
|||
|**Item**|**id@root**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis.id@root|
|**FHIR**|Condition\identifier\value@value|
|**Notes**|a UUID that acts as the identifier for the coded entry|
|||
|**Item**|**code@code**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\code@code|
|**FHIR**|Condition\code\coding\code@value|
|**Notes**|This will be one of the 4 COVID-19 diagnoses codes<br/>**1240751000000100**\|COVID\-19<br/>**1300721000000109**\|COVID\-19 confirmed by laboratory test<br/>**1300731000000106**\|COVID-19 confirmed using clinical diagnostic criteria<br/>**1240761000000102**\|Suspected COVID-19|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\code@codeSystem|
|**FHIR**|Condition\code\coding\system@value|
|**Notes**|HL7v3: fixed to "2.16.840.1.113883.2.1.3.2.4.15"<br/>FHIR: fixed to "http://snomed.info/sct"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\code\displayName|
|**FHIR**|Condition\code\coding\display@value|
|**Notes**|The display associated with the selected codes (as above in the Notes fro code@code|
|||
|**Item**|**statusCode.code@value**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\statusCode\code@value|
|**FHIR**|Condition\verificationStatus\code@value<br/>Condition\clinicalStatus\code@value
|**Notes**|FHIR:<br/>**normal**->clinicalStatus.active<br/>**nullified**->verificationStatus.entered-in-error<br/>**active**->clinicalStatus.active<br/>**completed**->verificationStatus.confirmed<br/>*Note: round-tipping from normal & active is not possible. This may be a clinical risk.*|
|||
|**Item**|**effectiveTime@value**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\effectiveTime\low@value<br/>UKCT_RM144042UK01.Diagnosis\effectiveTime\high@value|
|**FHIR**|Condition\onsetDateTime\value@value and Condition\abatementDateTime\value@value |
|**Notes**|HL7v3: Where known the dates that the diagnosis was affective on the patient should be used i.e when the patient started with asthma and when the asthma was no longer present for the patient.<br/>The date range shall be carried as follows:<br/>If both a start date and an end date are present the Date or Time Interval Complete data type shall be used:<br/>The *low* attribute shall contain the start date.<br/>The *high* attribute shall contain the end date.<br/>If only a start date is present the Date or Time Interval After data type shall be used:<br/>The *low* attribute shall contain the start date.<br/>FHIR: map low to onsetDateTime, map high to abatementDateTime|
|||
|**Item**|**value**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\value|
|**FHIR**|Observation\value[x]|
|**Notes**|defined as being "The value of the observation."<br/>FHIR: this should be modelled as a supporting Observation. Link an Observation from Condition\evidence\detail to an Observation resource. The Observation resource has the follwoubg element that are mandated:<br/>**Observation\status** - fix to either "unknown" if the status is unknown - or an appropriate status<br/>**Observation\code** - use the same code as used in Condition\code<br/>choose the appropriate **value[x]** data type to hiold the value of the Observation|
|||
|**Item**|**value**|
|**HL7v3**|UKCT_MT144042UK01.Diagnosis\value\pertinentInformation\pertinentSupportingInfo\value|
|**FHIR**|Condition\note|
|**Notes**|Supporting text for the Diagnosis|


### Example of HL7v3 Diagnoses

```xml
<UKCT_MT144042UK01.Diagnosis classCode="OBS" moodCode="EVN">
	<id root="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
	<code code="1300721000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="COVID-19 confirmed by laboratory test">
	</code>
	<statusCode code="normal"/>
	<effectiveTime>
		<low value="20200506104819"/>
	</effectiveTime>
      <pertinentInformation typeCode="PERT" contextConductionInd="true">
        <seperatableInd value="false"/>
        <pertinentSupportingInfo classCode="OBS" moodCode="EVN">
            <value>Problem; First, test</value>
            <code code="SupportingText" CodeSystem="2.16.840.1.113883.2.1.3.2.4.17.126" displayName="Supporting Text"/>
        </pertinentSupportingInfo>
    </pertinentInformation>
</UKCT_MT144042UK01.Diagnosis>
```

### Mapping to FHIR

```xml
<Condition xmlns="http://hl7.org/fhir">
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Condition" />
    </meta>
    <identifier>
        <value value="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
    </identifier>
    <clinicalStatus>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/condition-clinical" />
            <code value="active" />
            <display value="Active" />
        </coding>
    </clinicalStatus>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1300721000000109" />
            <display value="COVID-19 confirmed by laboratory test"/>
        </coding>
    </code>
    <onsetDateTime value="2020-05-06T10:48:19+00:00"/>
    <note>
        <text value="Problem; First, test"/>
    </note>
</Condition>
```

**The relevant paticipants for Diagnosis are author and informant. For details on how to populate participants see the [Mapping Participants](ParticipantCodedEntry) page.**

**PertinentInformation**

Note: This is a link class to supporting information. In terms of FHIR mapping, all the values here are fixed HL7v3 values, except the SupportingInfo.text, which maps to Condition.note

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|pertinentInformation@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "PERT"<br/>FHIR:no mapping|
|||
|**Item**|**@contextControlCode**|
|**HL7v3**|pertinentInformation@contextControlCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "true"<br/>FHIR:no mapping|
|||
|**Item**|**seperatableInd@value**|
|**HL7v3**|pertinentInformation.seperatableInd@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "false"<br/>FHIR:no mapping|

**SupportingInformation**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|SupportingInformation@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "OBS"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|SupportingInformation@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "EVN"|
|||
|**Item**|**code@code**|
|**HL7v3**|SupportingInformation.code@code|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "SupportingText"|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|SupportingInformation.code@coseSystem|
|**FHIR**|no mapping|
|**Notes**|HL7bv3: fixed to "2.16.840.1.113883.2.1.3.2.4.17.126"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|SupportingInformation.code@displayName|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "Supporting Text"|
|||
|**Item**|**value**|
|**HL7v3**|SupportingInformation.value|
|**FHIR**|Condition.note.text|
|**Notes**||

### HL7v3 Diagnoses example with supporting information

```xml
<UKCT_MT144042UK01.Diagnosis classCode="OBS" moodCode="EVN">
	<id root="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
	<code code="1300721000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="COVID-19 confirmed by laboratory test">
	</code>
	<statusCode code="normal"/>
	<effectiveTime>
		<low value="20200506104819"/>
	</effectiveTime>
    <pertinentInformation typeCode="PERT" contextConductionInd="true">
	    <seperatableInd value="false"/>
		<pertinentSupportingInfo classCode="OBS" moodCode="EVN">
			<value>Some Supporting Information</value>
			<code code="SupportingText" displayName="Supporting Text" codeSystem="2.16.840.1.113883.2.1.3.2.4.17.126"></code>
		</pertinentSupportingInfo>
	</pertinentInformation>
</UKCT_MT144042UK01.Diagnosis>
```

### FHIR Condition example with supporting information

```xml
<Condition xmlns="http://hl7.org/fhir">
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Condition" />
    </meta>
    <identifier>
        <value value="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
    </identifier>
    <clinicalStatus>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/condition-clinical" />
            <code value="active" />
            <display value="Active" />
        </coding>
    </clinicalStatus>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1300721000000109" />
            <display value="COVID-19 confirmed by laboratory test"/>
        </coding>
    </code>
    <onsetDateTime value="2020-05-06T10:48:19+00:00"/>
    <note> 
        <text value="Some Supporting Information"/>
    </note>
</Condition>
```

**PertinentInformation1**

Note: this is a link class to other information that may be referenced in the composition (or bundle).

All of the values here are HL7v3 fixed codes, and have no mapping to FHIR. The only FHIR mapping is from pertinentFinding\id, which maps to Condition\evidence\detail

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "PERT"<br/>FHIR: no mapping|
|||
|**Item**|**@inversionInd**|
|**HL7v3**|@inversionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "false"<br/>FHIR: no mapping|
|||
|**Item**|**negationInd**|
|**HL7v3**|pertinentInformation1@negationInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "false"<br/>FHIR: no mapping|
|||
|**Item**|**seperatableInd@value**|
|**HL7v3**|pertinentInformation1.seperatableInd@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "false"<br/>FHIR: no mapping|
|||
|**Item**|**templateId\root@value**|
|**HL7v3**|pertinentInformation1\root@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"<br/>FHIR: no mapping|
|||
|**Item**|**templateId\extension@value**|
|**HL7v3**|pertinentInformation1\extension@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "CSAB_RM-NPfITUK10.sourceOf1"<br/>FHIR: no mapping|

**Finding**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|Finding@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "OBS"<br/>FHIR: no mapping|
|||
|**Item**|**@moodCode**|
|**HL7v3**|Finding@moodCode|
|**FHIR**|no mapping|
|**Notes**|Hl7v3: fixed to "EVN"<br/>FHIR: no mapping|
|||
|**Item**|**id@root**|
|**HL7v3**|Finding@root|
|**FHIR**|Condition\evidence\detail|
|**Notes**|FHIR: use the evidence\detail reference to link to any relevant Findings in the bundle|

### HL7v3 Example of reference to a Finding

```xml
<UKCT_MT144042UK01.Diagnosis classCode="OBS" moodCode="EVN">
	<id root="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
	<code code="1300721000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="COVID-19 confirmed by laboratory test">
	</code>
	<statusCode code="normal"/>
	<effectiveTime>
		<low value="20200506104819"/>
	</effectiveTime>
	<pertinentInformation1 typeCode="PERT" inversionInd="false" negationInd="false">
	    <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.sourceOf1"/>
		<seperatableInd value="false"/>
		<pertinentFinding classCode="OBS" moodCode="EVN">
			<id root="50E3A850-8F89-11EA-BE46-00155DC3FA77"></id>
		</pertinentFinding>
	</pertinentInformation1>
</UKCT_MT144042UK01.Diagnosis>
```

### FHIR Example of reference to a Finding

```xml
<Condition xmlns="http://hl7.org/fhir">
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Condition" />
    </meta>
    <identifier> 
        <value value="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
    </identifier>
    <clinicalStatus>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/condition-clinical" />
            <code value="active" />
            <display value="Active" />
        </coding>
    </clinicalStatus>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1300721000000109" />
            <display value="COVID-19 confirmed by laboratory test"/>
        </coding>
    </code>
    <onsetDateTime value="2020-05-06T10:48:19+00:00"/>
    <evidence>
        <detail>
		   <reference value="50E3A850-8F89-11EA-BE46-00155DC3FA77"/>
        </detail>
    </evidence>
</Condition>
```
