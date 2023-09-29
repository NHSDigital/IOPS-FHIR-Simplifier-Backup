#### Patient carer correspondence

### CRE Type 163181000000107 \| Patient/carer correspondence - care record element (record artifact) (uses Communication)

```xml
<entry>
	<fullUrl value="urn:uuid:3b3f207f-be82-4ffb-924e-9be0966f5c65"/>
<resource>
    <Communication>
		<id value="3b3f207f-be82-4ffb-924e-9be0966f5c65"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Communication" />
        </meta>
        <status value="completed"/>
        <topic>
            <coding>
                <code value="1240781000000106"/>
                <system value="http://snomed.info/sct"/>
                <display value="Severe acute respiratory syndrome coronavirus 2 vaccination invitation short message service text message sent (situation)"/>
            </coding>
        </topic>
        <sent value="2020-08-05"/>
	</Communication>
</resource>
</entry>
```

### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
		<code code="163181000000107" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Patient/carer correspondence"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144035UK01.PatientCarerCorrespondence classCode="DOC" moodCode="EVN">
				<id root="0F582D83-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240781000000106" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Severe acute respiratory syndrome coronavirus 2 vaccination invitation short message service text message sent (situation)">
				</code>
				<statusCode code="normal"/>
				<effectiveTime value="20200805"/>
			</UKCT_MT144035UK01.PatientCarerCorrespondence>
		</component>
	</pertinentCREType>
</pertinentInformation2>
```
