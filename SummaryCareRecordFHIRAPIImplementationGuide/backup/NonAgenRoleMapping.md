## NonAgentRole Mapping

This page shows the commonly used author role class NonAgentRole mapping to FHIR.

This page will be referenced from the appropriate CRETypes pages.

**NonAgent**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|NonAgentRole@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ROL"|
|||
|**Item**|**id@root**|
|**HL7v3**|NonAgentRole.id@root|
|**FHIR**|RelatedPerson\identifier\system\@value|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.4.1"<br/>FHIR: Fixed to "https://fhir.nhs.uk/Id/nhs-number"|
|||
|||
|**Item**|**id@extension**|
|**HL7v3**|NonAgentRole.id@extension|
|**FHIR**|RelatedPerson\identifier\value\@value|
|**Notes**|NHS Number|
|||
|||
|**Item**|**code@code**|
|**HL7v3**|NonAgentRole.code@code|
|**FHIR**|RelatedPerson\relationship\coding\code@value|
|**Notes**||
|||
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|NonAgentRole.code@codeSystem|
|**FHIR**|RelatedPerson\relationship\coding\system@value|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.16.15"<br/>FHIR: Fixed to "https://fhir.nhs.uk/STU3/ValueSet/PersonRelationshipType-1"|
|||
|||
|**Item**|**code@displayName**|
|**HL7v3**|NonAgentRole.code@displayName|
|**FHIR**|RelatedPerson\relationship\coding\display@value|
|**Notes**||


**Note** if a nonAgentPerson is linked from from the nonAgentRole, then in FHIR terms, use the Person\link\target to link this RelatedPerson to Person resource.

**NonAgentPerson**

||Mapping|
|--
|**Item**|@classCode|
|**HL7v3**|NonAgenPerson@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "PSN"|
|||
|**Item**|@determinerCode|
|**HL7v3**|NonAgenPerson@determinerCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|name|
|**HL7v3**|NonAgenPerson.name|
|**FHIR**|RelatedPerson.name|
|**Notes**||

**HL7v3 example of NonAgentRole in a Finding**
```xml
<UKCT_MT144043UK02.Finding classCode="OBS" moodCode="EVN">
	<id root="D745F1E0-6DF2-11EA-AE26-C5CB3F0B33D1"/>
	<code code="397686008" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Sense of smell, function">
		<originalText>Sense of smell</originalText>
	</code>
	<statusCode code="completed"/>
	<effectiveTime>
		<low value="20200324171258"/>
	</effectiveTime>
	
	<informant typeCode="INF" contextControlCode="OP">
		<time value="20160630103358"/>
		<participantNonAgentRole classCode="ROL">
			<code code="01" displayName="Brother" codeSystem="2.16.840.1.113883.2.1.3.2.4.16.15"></code>
			<playingNonAgentPerson classCode="PSN" determinerCode="INSTANCE">
				<name>JONES Bob</name>
			</playingNonAgentPerson>
		</participantNonAgentRole>
	</informant>
</UKCT_MT144043UK02.Finding>
```


**HL7v3**
```xml
<participantNonAgentRole classCode="ROL">
	<code code="15" displayName="Brother" codeSystem="2.16.840.1.113883.2.1.3.2.4.16.15"></code>
	<playingNonAgentPerson classCode="PSN" determinerCode="INSTANCE">
		<name>BLOGGS Bill</name>
	</playingNonAgentPerson>
</participantNonAgentRole>
```

**FHIR**
```xml
<RelatedPerson>
    <patient>
        <reference value="f97eff4a-162c-4336-992e-ef669e8c0481"/>
    </patient>
    <relationship>
        <coding>
            <code value="15"/>
            <system value="https://fhir.nhs.uk/STU3/ValueSet/PersonRelationshipType-1"/>
            <display value="Brother"/>
        </coding>
    <relationship>
    <name>
        <family value="BLOGGS"/>
        <given value="Bill"/>
    </name>
</RelatedPerson>
```