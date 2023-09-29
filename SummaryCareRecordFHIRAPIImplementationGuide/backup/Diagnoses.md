#### Diagnoses

### CRE Type 163001000000103 \| Diagnoses - care record element (record artifact) (uses Condition)

```xml
<entry>
	<fullUrl value="urn:uuid:bdb64d63-9c06-44fd-b2c1-324c580c6142"/>
<resource>
    <Condition>
		<id value="bdb64d63-9c06-44fd-b2c1-324c580c6142"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        </meta>
		<identifier>
			<value value="AF0AAF00-797C-11EA-B378-F1A7EC384595"/>
		<identifier>
        <clinicalStatus>
            <coding>
                <system value="http://terminology.hl7.org/CodeSystem/condition-clinical" />
                <code value="active" />
                <display value="Active" />
            </coding>
        </clinicalStatus>
        <code>
            <coding>
                <system value="http://snomed.info/sct"/>
                <code value="1300721000000109"/>
                <display value="COVID-19 confirmed by laboratory test"/>
            </coding>
        </code>
        <onsetDateTime value="2020-08-05"/>
    </Condition>
</resource>
</entry>
```
### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
		<code code="163001000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Diagnoses"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144042UK01.Diagnosis classCode="OBS" moodCode="EVN">
				<id root="AF0AAF00-797C-11EA-B378-F1A7EC384595"/>
				<code code="1300721000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="COVID-19 confirmed by laboratory test">
				</code>
				<statusCode code="normal"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
				</pertinentInformation>
			</UKCT_MT144042UK01.Diagnosis>
		</component>
	</pertinentCREType>
</pertinentInformation2>
```
