#### Provision of advice and guidance

### CRE Type 163101000000102 \| Provision of advice and information to patients and carers - care record element (record artifact) (uses Communication)

```xml
<entry>
	<fullUrl value="urn:uuid:8e8acd76-9a1c-44de-ac88-30254abdee4a"/>
<resource>
    <Communication>
		<id value="8e8acd76-9a1c-44de-ac88-30254abdee4a"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Communication" />
        </meta>
        <status value="completed"/>
        <topic>
            <coding>
                <code value="1240711000000104"/>
                <system value="http://snomed.info/sct"/>
                <display value="Educated about severe acute respiratory syndrome coronavirus 2 infection (situation)"/>
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
		<code code="163101000000102" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Provision of Advice and Information to Patients and Carers"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144049UK01.ProvisionOfAdviceAndInformation classCode="INFRM" moodCode="EVN">
				<id root="0F582D83-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240711000000104" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Educated about severe acute respiratory syndrome coronavirus 2 infection (situation)">
				</code>
				<statusCode code="normal"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
			</UKCT_MT144049UK01.ProvisionOfAdviceAndInformation>
		</component>
	</pertinentCREType>
</pertinentInformation2>
```