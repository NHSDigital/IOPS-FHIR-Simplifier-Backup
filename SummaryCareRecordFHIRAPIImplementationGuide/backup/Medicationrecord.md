#### Medication record

## CRE Type 163111000000100 \| Medication record - care record element (record artifact) (as all the medication record COVID-19 entries are vaccine related, this CRE Type for COVID-19 uses Immunization)

**Note** as the immunisation is a procedure (not done), the Extension-CareConnect-VaccinationProcedure-1 is used.

```xml
<entry>
	<fullUrl value="urn:uuid:d998d083-64d7-42d0-8bf4-1a5770d84c4f"/>
<resource>
    <Immunization>
		<id value="d998d083-64d7-42d0-8bf4-1a5770d84c4f"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization" />
        </meta>
		<extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure">
			<valueCodeableConcept>
				<coding>
					<system value="http://snomed.info/sct"/>
					<code value="1240681000000103"/>
					<display value="Severe acute respiratory syndrome coronavirus 2 vaccination not done (situation)"/>
				</coding>
			</valueCodeableConcept>
		</extension>        
        <status value="not-done"/>
		<vaccineCode>
			<coding>
				<system value="http://terminology.hl7.org/CodeSystem/v3-NullFlavor"/>
				<code value="UNK"/>
				<display value="Unknown"/>
			</coding>
		</vaccineCode>   
        <patient>
            <reference value="urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc/>
        </patient>    
        <occuranceDateTime value="2020-0805"/>
    </Observation>
</resource>
</entry>
```

### Equivalent HL7v3 coded entry
**Note:** Medication record is not a supported Summary Care Record CRE Type. Non-supported SCR CRE Types use the "default" Clinical Observations and Findings CRE Type.

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
				<code code="1240681000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Severe acute respiratory syndrome coronavirus 2 vaccination not done (situation)">
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
