#### Finding Coded Entry

The Finding CMET covers 1240581000000104 \| SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive.

The Finding CMET covers Observations for Blood Pressure, Weight, Height, Temerature, FindingOrganizer as well a general Finding class. As the COVID entry will only appear under the general Finding class, its is just this that class that is documented here.

The Finding class has an option to apply a ReferenceValue (a reference range). As the COVID entry is a statement, the reference range is not relevant, so is not documented here. 

Finding is mapped to the FHIR Observation resource

**Finding**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT144043UK02.Finding@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "OBS"<br/>FHIR: no mapping|
|||
|**Item**|**@moodCode**|
|**HL7v3**|UKCT_MT144043UK02.Finding@moodCode|
|**FHIR**|no mapping|
|**Notes**|Hl7v3: Fixed to "EVN"<br/>FHIR: no mapping|
|||
|**Item**|**id@root**|
|**HL7v3**|UKCT_MT144043UK02.Finding.id@root|
|**FHIR**|Observation\identifier\value@value|
|**Notes**|HL7v3: a UUID|
|||
|**Item**|**code@code**|
|**HL7v3**|UKCT_MT144043UK01.Finding\code@code|
|**FHIR**|Observation\code\coding\code@value|
|**Notes**|The only use case documented to to carry 1240581000000104 \| SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|UKCT_MT144043UK02.Finding\code@codeSystem|
|**FHIR**|Observation\code\coding\system@value|
|**Notes**|HL7v3: fixed to "2.16.840.1.113883.2.1.3.2.4.15"<br/>FHIR: fixed to "http://snomed.info/sct"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|UKCT_MT144043UK02.Finding\code\displayName|
|**FHIR**|Observation\code\coding\display@value|
|**Notes**|see item code@code above|
|||
|**Item**|**statusCode.code@value**|
|**HL7v3**|UKCT_MT144043UK02.Finding.statusCode.code@value|
|**FHIR**|Observation\status\code@value
|**Notes**|FHIR<br/>normal->final<br/>nullified->entered-in-error<br/>active->final<br/>completed->final <br/>*Note that this cannot be round-tripped & may be clinically unsafe*|
|||
|**Item**|**effectiveTime@value**|
|**HL7v3**|UKCT_MT144043UK02.Finding.effectiveTime@value|
|**FHIR**|Observation\effective[x] - see Notes|
|**Notes**|Hl7v3: A date range shall be carried as follows:<br/>If both a start date and an end date are present the Date or Time Interval Complete datatype shall be used:<br/>The *low* attribute shall contain the start date<br/>The *high* attribute shall contain the end date.<br/>If only a start date is present the Date or Time Interval After datatype shall be used:<br/>The *low* attribute shall contain the start date.<br/>If only an end date is present the Date or Time Interval Before datatype shall be used:<br/>The *high* attribute shall contain the end date.<br/>The *center* attribute may be used if the exact start / end time is not known<br/>The *center* attribute shall contain a time stamp.<br/>FHIR:When mapping *low* or *high*, use effectivePeriod (low=start; high=end), when mapping *centre* then map to effectiveDateTime@value|
|||
|**Item**|**value**|
|**HL7v3**|UKCT_MT144043UK02.Finding.value|
|**FHIR**|Observation\status\value[x]|
|**Notes**|FHIR:this is information in support of the coded value, using an appropriate data type from value[x]|

### HL7v3 example
```xml
<UKCT_MT144043UK02.Finding classCode="OBS" moodCode="EVN">
	<id root="0F582D92-8F89-11EA-8B2D-B741F13EFC47"/>
	<code code="1240581000000104" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive">
	</code>
	<statusCode code="completed"/>
	<effectiveTime>
		<low value="20200506104819"/>
	</effectiveTime>
</UKCT_MT144043UK02.Finding>
```

### FHIR example
```xml
<Observation>
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Observation" />
    </meta>    
	<identifier>
		<value value="0F582D92-8F89-11EA-8B2D-B741F13EFC47"/>
	</identifier>
	<status value="final"/>
	<code>
		<coding>
			<code value="1240581000000104"/>
			<display value="SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive"/>
			<system value="http://snomed.info/sct"/>
		</coding>
	</code>
	<effectivePeriod>
		<start value="2020-05-06T10:48:19+00:00"/>
	</effectivePeriod>
</Observation>
```
### For an &lt;effectiveTime&gt;&lt;centre&gt; mapping use Observation.effectiveDateTime

```xml
<Observation>
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Observation" />
    </meta>    
	<identifier>
		<value value="0F582D92-8F89-11EA-8B2D-B741F13EFC47"/>
	</identifier>
	<status value="final"/>
	<code>
		<coding>
			<code value="1240581000000104"/>
			<display value="SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) RNA (ribonucleic acid) detection result positive"/>
			<system value="http://snomed.info/sct"/>
		</coding>
	</code>
	<effectiveDateTime value="2020-05-06T10:48:19+00:00"/>
</Observation>
```



**The relevant paticipants for Finding are author, informant and performer. For details on how to populate participants link classes see the [ParticipantCodedEntry](ParticipantCodedEntry) page. For the Role details see 
* [RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping](RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping)
* [RAgentNPFITDeviceUKCTRM120600UK02Mapping](RAgentNPFITDeviceUKCTRM120600UK02Mapping)
* [NonAgenRoleMapping](NonAgenRoleMapping)**
