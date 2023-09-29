#### Clinical observations and findings

### CRE Type 163131000000108 \| Clinical observations and findings - care record element (record artifact) (uses Observation)

```xml
<entry>
	<fullUrl value="urn:uuid:b725e8c8-c397-453b-82fa-37a1eb29a690"/>
<resource>
    <Observation>
		<id value="b725e8c8-c397-453b-82fa-37a1eb29a690"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        </meta>
        <status value="final"/>
        <code>
            <coding>
                <system value="http://snomed.info/sct"/>
                <code value="1240601000000108"/>
                <display value="High priority for severe acute respiratory syndrome coronavirus 2 vaccination (finding)"/>
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
		<code code="163131000000108" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Clinical Observations and Findings"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144043UK02.Finding classCode="OBS" moodCode="EVN">
				<id root="19ABC6D1-8AF5-11EA-9FCE-AFDCAECF9DFB"/>
				<code code="1240601000000108" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="High priority for severe acute respiratory syndrome coronavirus 2 vaccination (finding)">
				</code>
				<statusCode code="completed"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
			</UKCT_MT144043UK02.Finding>
		</component>
	</pertinentCREType>
</pertinentInformation2>
```				