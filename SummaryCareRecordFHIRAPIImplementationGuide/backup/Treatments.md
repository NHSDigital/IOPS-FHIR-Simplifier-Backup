#### Treatments

### CRE Type 163071000000106 \|  Treatments - care record element (record artifact) (uses Procedure)

```xml
<entry>
	<fullUrl value="urn:uuid:870bfee5-67e6-4611-8b62-e4609e2f3105"/>
<resource>
    <Procedure>
		<id value="870bfee5-67e6-4611-8b62-e4609e2f3105"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure" />
    </meta>
        <status value="completed" />
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="1240491000000103" />
            <display value="Severe acute respiratory syndrome coronavirus 2 vaccination (procedure)" />
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
		<code code="163071000000106" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Treatments"/>
		<component typeCode="COMP" contextConductionInd="true">
		<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
			<seperatableInd value="false"/>
			<UKCT_MT144055UK01.Treatment classCode="PROC" moodCode="EVN">
				<id root="0F5A9E72-8F89-11EA-8B2D-B741F13EFC47"/>
				<code code="1240491000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Severe acute respiratory syndrome coronavirus 2 vaccination (procedure)">
				</code>
				<statusCode code="normal"/>
				<effectiveTime>
					<low value="20200805"/>
				</effectiveTime>
			</UKCT_MT144055UK01.Treatment>
		</component>
	</pertinentCREType>
</pertinentInformation2>
```