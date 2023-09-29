#### Risk to patient

### CRE Type 163231000000100 \| Risks to patient - care record element (record artifact) (uses Observation)

```xml
<entry>
<fullUrl value="urn:uuid:36c913f3-b0a8-4bf6-b84d-a3dec49b41d1"/>
<resource>
    <Observation>
		<id value="36c913f3-b0a8-4bf6-b84d-a3dec49b41d1"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        </meta>
        <status value="final"/>
        <code>
            <coding>
                <system value="http://snomed.info/sct"/>
                <code value="1240431000000104"/>
                <display value="Exposure to severe acute respiratory syndrome coronavirus 2 infection (event)"/>
            </coding>
        </code>
        <effectiveDateTime value="2020-08-05"/>
    </Observation>
</resource>	
</entry>
```

### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
	<code code="163231000000100" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Risks to Patient"/>
	<component typeCode="COMP" contextConductionInd="true">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
	<seperatableInd value="false"/>
	<UKCT_MT144054UK01.RiskToPatient classCode="OBS" moodCode="EVN">
	<id root="10CE2F30-8AF5-11EA-9FCE-AFDCAECF9DFB"/>
	<code code="1240441000000108" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Close exposure to severe acute respiratory syndrome coronavirus 2 infection (event)"/>
	<statusCode code="normal"/>
	<effectiveTime>
		<low value="20200805"/>
	</effectiveTime>
	</UKCT_MT144054UK01.RiskToPatient>
	</component>
	</pertinentCREType>
</pertinentInformation2>
```