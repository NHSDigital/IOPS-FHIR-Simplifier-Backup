#### Care Events

### CRE Type 162951000000105 \| Care events - care record element (record artifact) (uses Encounter)

```xml
<entry>
<fullUrl value="urn:uuid:722e35ec-0f00-4b71-b1f9-2240623c6b41"/>
<resource>
	<Encounter>
		<id value="722e35ec-0f00-4b71-b1f9-2240623c6b41"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter" />
        </meta>	
		<status value="finished"/>
		<class>
			<code value="GENRL">
			<system value="http://terminology.hl7.org/CodeSystem/v3-ActCode"/>
			<display value="General"/>
		</class>
		<type>
			<coding>
				<code value="1240631000000102">
				<system value="http://snomed.info/sct"/>
				<display value="Did not attend SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccination"/>
			</coding>
		</type>
		<period>
			<end value="2020-08-05"/>
		</period>
	</Encounter>
</resource>
</entry>
```

### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
		<code code="162951000000105" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Care Events"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144037UK01.CareEvent classCode="ENC" moodCode="EVN">
				<id root="0F582D91-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240631000000102" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Did not attend SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccination">
				</code>
				<statusCode code="normal"/>
				<effectiveTime>
					<low value="20200805"/>
					</effectiveTime>
			</UKCT_MT144037UK01.CareEvent>
		</component>
    </pertinentCREType>
</pertinentInformation2>
```				