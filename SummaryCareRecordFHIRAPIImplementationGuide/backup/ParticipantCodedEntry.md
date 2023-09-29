#### Participant Coded Entry

The participant types allowed for **Diagnoses** are<br/>
* author
* informant

The participant types allowed for **Finding** are <br/>
* author
* informant
* performer

For Diagnoses & Finding authors are described using the HL7v3 CMET [R_AgentNPFITPersonGeneral (UKCT_RM160018UK01)]( RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping). Findings also allow authors to be described as a device [R_AgentNPFITDevice (UKCT_RM120600UK02)](RAgentNPFITDeviceUKCTRM120600UK02Mapping).

Informants are described for both Diagnoses & Fings as being a [R_AgentNPFITPersonGeneral (UKCT_RM160018UK01)]( RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping), or a [NonAgentRole](NonAgenRoleMapping).

Performers are described as being [R_AgentNPFITPersonGeneral (UKCT_RM160018UK01)]( RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping).

### Participant link classes 

Note: FHIR resources carry a limited number of participation types. In particular, FHIR resources often lack the dates of participantion - for example the Condition resource allows you to record the asserter (informant), but not the date of assertion. In order to give a consistent approach to participations, the Encounter resource is used, in particular the participant backbone element to link to relevant participants.

<div class="summary-structure-img">
{{render:Participants}}
</div>

**author**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|author@typeCode|
|**FHIR**|Encounter\participant\type\coding\code@value|
|**Notes**|HL7v3:fixed to "AUT"<br/>FHIR: code@value="AUT"<br/>system@value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"<br/>display.value="author"|
|||
|**Item**|**@contextControlCode**|
|**HL7v3**|author@contextControlCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3:fixed to "OP"|
|||
|**Item**|**time@value**|
|**HL7v3**|author.time@value|
|**FHIR**|Encounter.participant.period.start@value|
|**Notes**||

### HL7v3 example

```xml
<author typeCode="AUT" contextControlCode="OP">
	<time value="20200506104819"/>
	<!--roles go here-->
</author>
```

### FHIR example
```xml
<Encounter>
    <!--Encounter must have values for status & class - so fix as shown-->
    <status value="finished"/>
    <class>
        <code value="UNK"/>
        <system value="http://terminology.hl7.org/CodeSystem/v3-NullFlavor"/>
        <display value="Unknown"/>
    </class>
    <participant>
        <type>
            <coding>
                <code value="AUT"/>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"/>
                <display value="author"/>
            </coding>
        </type>
        <period>
            <start value="2020-05-06T10:48:19+00:00"/>
        </period>
        <individual>
            <!--A link to the participation-->
            <reference value="cb9694ea-36f1-4e33-87cc-361409d251c6"/>
        </individual>
    </participant>
</Encounter>
```

**performer**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|performer@typeCode|
|**FHIR**|Encounter\participant\type\coding\code@value|
|**Notes**|HL7v3: fixed to "PRF"<br/>FHIR: code@value="PRF"<br/>system@value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"<br/>display.value="performer"|
|||
|**Item**|**@contextControlCode**|
|**HL7v3**|performer@contextControlCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "OP"|
|||
|**Item**|**time@value**|
|**HL7v3**|performer.time@value|
|**FHIR**|Encounter.participant.period.start@value|
|**Notes**||
|||
|**Item**|**modeCode.code@code**|
|**HL7v3**|performer.modeCode.code@code|
|**FHIR**|Encounter.participant.[extensionModeCode] - see below|
|**Notes**||

**Example of the modeCode extension**
```xml
<extension url="https://fhir.nhs.uk/StructureDefinition/Extension-SCR-ModeCode">
    <valueCodeableConcept>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationMode" />
            <code value="PHYSICAL" />
            <display value="physical presence" />
        </coding>
    </valueCodeableConcept>
</extension>
```

**modeCode in an Encounter example**
```xml
<Encounter>
    <!--Encounter must have values for status & class - so fix as shown-->
    <status value="finished"/>
    <class>
        <code value="UNK"/>
        <system value="http://terminology.hl7.org/CodeSystem/v3-NullFlavor"/>
        <display value="Unknown"/>
    </class>
    <participant>
    <extension url="https://fhir.nhs.uk/StructureDefinition/Extension-SCR-ModeCode">
        <valueCodeableConcept>
            <coding>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationMode" />
                <code value="PHYSICAL" />
                <display value="physical presence" />
            </coding>
        </valueCodeableConcept>
    </extension>    
        <type>
            <coding>
                <code value="PRF"/>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"/>
                <display value="performer"/>
            </coding>
        </type>
        <period>
            <start value="2020-05-06T10:48:19+00:00"/>
        </period>
        <individual>
            <!--A link to the participation-->
            <reference value="cb9694ea-36f1-4e33-87cc-361409d251c6"/>
        </individual>
    </participant>
</Encounter>
```
**HL7v3 Performer Example (with modeCode)**
```xml
	<performer typeCode="PRF" contextControlCode="OP">
		<time value="20160630103358"/>
		<modeCode code="PHYSICAL" codeSystem="2.16.840.1.113883.5.1064"/>
		<UKCT_MT160018UK01.AgentPersonSDS classCode="AGNT">
			<id root="1.2.826.0.1285.0.2.0.67" extension="173067658018"></id>
			<agentPersonSDS classCode="PSN" determinerCode="INSTANCE">
				<id root="1.2.826.0.1285.0.2.0.65" extension="784578436584"></id>
				<name>JONES Bob</name>
			</agentPersonSDS>
		</UKCT_MT160018UK01.AgentPersonSDS>
	</performer>
```
**Maps to FHIR Encounter.participant**
```xml
    <participant>
    <extension url="https://fhir.nhs.uk/StructureDefinition/Extension-SCR-ModeCode">
        <valueCodeableConcept>
            <coding>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationMode" />
                <code value="PHYSICAL" />
                <display value="physical presence" />
            </coding>
        </valueCodeableConcept>
    </extension>    
        <type>
            <coding>
                <code value="PRF"/>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"/>
                <display value="performer"/>
            </coding>
        </type>
        <individual>
            <!--A link to the participation where you find the name, SDS id, Job Role code etc.-->
            <reference value="cb9694ea-36f1-4e33-87cc-361409d251c6"/>
        </individual>
    </participant>
```

**Informant**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|informant@typeCode|
|**FHIR**|Encounter\participant\type\coding\code@value|
|**Notes**|HL7v3: fixed to "INF"<br/>FHIR: code@value="INF"<br/>system@value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"<br/>display.value="informant"|
|||
|**Item**|**@contextControlCode**|
|**HL7v3**|informant@contextControlCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: fixed to "OP"|
|||
|**Item**|**time@value**|
|**HL7v3**|informant.time@value|
|**FHIR**|Encounter.participant.period.start@value|
|**Notes**||

**Hl7v3 Example**
```xml
<informant typeCode="INF" contextControlCode="OP">
	<time value="20160630103358"/>
	<UKCT_MT160018UK01.AgentPersonSDS classCode="AGNT">
		<id root="1.2.826.0.1285.0.2.0.67" extension="173067658018"></id>
		<agentPersonSDS classCode="PSN" determinerCode="INSTANCE">
			<id root="1.2.826.0.1285.0.2.0.65" extension="784578436584"></id>
		<name>JONES Bob</name>
	</agentPersonSDS>
	</UKCT_MT160018UK01.AgentPersonSDS>
</informant>
```

### FHIR example
```xml
<Encounter>
    <!--Encounter must have values for status & class - so fix as shown-->
    <status value="finished"/>
    <class>
        <code value="UNK"/>
        <system value="http://terminology.hl7.org/CodeSystem/v3-NullFlavor"/>
        <display value="Unknown"/>
    </class>
    <participant>
        <type>
            <coding>
                <code value="INF"/>
                <system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"/>
                <display value="informant"/>
            </coding>
        </type>
        <period>
            <start value="2020-05-06T10:48:19+00:00"/>
        </period>
        <individual>
            <!--A link to the participation-->
            <reference value="cb9694ea-36f1-4e33-87cc-361409d251c7"/>
        </individual>
    </participant>
</Encounter>
```

**FHIR example showing bundle links to Encounter**
```xml
<Bundle xmlns="http://hl7.org/fhir">
	<id value="UKCore-Bundle-BundledAllergyList-Example"/>
	<type value="collection"/>
	<entry>
		<resource>
			<Composition>
				<!--Composition header bits go here-->
				<section>
					<title value="Diagnoses"/>
					<text>
						<!--section text goes here-->
					</text>
					<entry>
						<!--link to the coded data fro Diagnoses-->
						<reference value="urn:uuid:e5fc3307-eac7-4665-99f7-dc6ac9f72910"/>
					</entry>
				</section>
				<!--Rest of composition goes here-->
			</Composition>
		</resource>
	</entry>
	
	<!--A diagnosis-->
	<entry>
		<fullUrl value="urn:uuid:e5fc3307-eac7-4665-99f7-dc6ac9f72910"/>
		<resource>
			<Condition>
				<id value="e5fc3307-eac7-4665-99f7-dc6ac9f72910"/>
				<meta>
					<profile value="https://fhir.nhs.uk/StructureDefinition/UKCore-Condition"/>
				</meta>
				<identifier value="0F582D97-8F89-11EA-8B2D-B741F13EFC47"/>
				<clinicalStatus>
					<coding>
						<system value="http://terminology.hl7.org/CodeSystem/condition-clinical"/>
						<code value="active"/>
						<display value="Active"/>
					</coding>
				</clinicalStatus>
				<code>
					<coding>
						<system value="http://snomed.info/sct"/>
						<code value="1300721000000109"/>
						<display value="COVID-19 confirmed by laboratory test"/>
					</coding>
				</code>
				<!--link to the encounter to link in participants-->
				<encounter>
					<reference value="urn:uuid:a0205cd2-e56d-4c3b-92c0-d1c0a7b389cb"/>
				</encounter>
				<onsetDateTime value="2020-05-06T10:48:19+00:00"/>
			</Condition>
		</resource>
	</entry>
	
	<!--the Encounter containing the participant links-->
	<entry>
		<fullUrl value="urn:uuid:e5fc3307-eac7-4665-99f7-dc6ac9f72910"/>
		<resource>
			<Encounter>
				<status value="finished"/>
				<class>
					<code value="UNK"/>
					<system value="http://terminology.hl7.org/CodeSystem/v3-NullFlavor"/>
					<display value="Unknown"/>
				</class>
				<!--an Author-->
				<participant>
					<type>
						<coding>
							<code value="AUT"/>
							<system value="http://terminology.hl7.org/CodeSystem/v3-ParticipationType"/>
							<display value="author"/>
						</coding>
					</type>
					<period>
						<start value="2020-05-06T10:48:19+00:00"/>
					</period>
					<individual>
						<!--A link to the participation-->
						<reference value="urn:uuid:cb9694ea-36f1-4e33-87cc-361409d251c6"/>
					</individual>
				</participant>
			</Encounter>
		</resource>
	</entry>
	
	<!--the paractitioner playing the author-->
	<entry>
		<fullUrl value="urn:uuid:cb9694ea-36f1-4e33-87cc-361409d251c6"/>
		<resource>
			<PractitionerRole>
				<id value="83c26c8f-ee72-4534-8891-0136972b2106"/>
				<identifier>
					<system value="http://fhir.nhs.net/Id/sds-role-profile-id"/>
					<value value="123456"/>
				</identifier>
				<practitioner>
					<reference value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				</practitioner>
			</PractitionerRole>
		</resource>
	</entry>
	
	<entry>
		<fullUrl value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
		<resource>
			<Practitioner>
				<id value="b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				<identifier>
					<system value="https://fhir.nhs.uk/Id/sds-user-id"/>
					<value value="RT555"/>
				</identifier>
				<name>
					<family value="BLOGGS"/>
					<given value="Fred"/>
				</name>
			</Practitioner>
		</resource>
	</entry>
</Bundle>
```


