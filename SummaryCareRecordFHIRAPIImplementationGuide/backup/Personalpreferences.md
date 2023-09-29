#### Personal preferences

### CRE Type 162961000000108 \|  Personal preferences - care record element (record artifact) (uses Observation)

```xml
<entry>
	<fullUrl value="urn:uuid:5a3ead29-446d-4ad8-8a2f-aa50a3d026bb"/>
<resource>
    <Observation>
		<id value="5a3ead29-446d-4ad8-8a2f-aa50a3d026bb"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        </meta>
        <status value="final"/>
        <code>
            <coding>
                <system value="http://snomed.info/sct"/>
                <code value="1240651000000109"/>
                <display value="Severe acute respiratory syndrome coronavirus 2 vaccination declined (situation)"/>
            </coding>
        </code>
        <effectiveDateTime value="2020-08-05"/>
    </Observation>
</entry>
```

### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
		<code code="162961000000108" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Personal Preferences"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144046UK01.PersonalPreference classCode="OBS" moodCode="EVN">
				<id root="0F5A9E73-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240651000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccination declined">
					<originalText>Severe acute respiratory syndrome coronavirus 2 vaccination declined (situation)</originalText>
				</code>
				<statusCode code="completed"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
			</UKCT_MT144046UK01.PersonalPreference>
		</component>
	</pertinentCREType>
</pertinentInformation2>