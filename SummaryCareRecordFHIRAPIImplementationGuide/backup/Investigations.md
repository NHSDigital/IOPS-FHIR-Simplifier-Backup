#### Investigations

### CRE Type 163081000000108 \|  Investigations - care record element (record artifact) (uses Procedure)

```xml
<entry>
	<fullUrl value="urn:uuid:3fcf3797-8b3d-4d4f-a59a-b43b7615e51d"/>
<resource>
    <Procedure>
		<id value="3fcf3797-8b3d-4d4f-a59a-b43b7615e51d"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure" />
    </meta>
        <status value="completed" />
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1240461000000109" />
            <display value="Measurement of severe acute respiratory syndrome coronavirus 2 antibody (procedure)" />
        </coding>
    </code>
    <performedDateTime value="2020=08-05" />
	</Procedure>
</resource>
</entry>
```
### Equivalent HL7v3 coded entry
```xml
<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
	<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
	<seperatableInd value="true"/>
	<pertinentCREType classCode="CATEGORY" moodCode="EVN">
		<code code="163081000000108" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Investigations"/>
		<component typeCode="COMP" contextConductionInd="true">
			<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144045UK01.Investigation classCode="PROC" moodCode="EVN">
				<id root="0F5A9E75-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240461000000109" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Measurement of severe acute respiratory syndrome coronavirus 2 antibody (procedure)">
				</code>
				<statusCode code="normal"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
			</UKCT_MT144045UK01.Investigation>
		</component>
	</pertinentCREType>
</pertinentInformation2>

```
