#### Medication recommendations

### CRE Type 185371000000109 \|  Medication recommendations - care record element (record artifact) (this example uses ImmunizationRecommendation. Other examples may use alternative FHIR resources)

```xml
<entry>
	<fullUrl value="urn:uuid:2e33e466-7e52-42c8-86ce-7c488d067965"/>
<resource>
    <ImmunizationRecommendation>
		<id value="2e33e466-7e52-42c8-86ce-7c488d067965"/>
        <patient>
            <reference value="urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc/>
        </patient>
        <date value="2020-08-05"/>
        <recommendation>
            <contraindicatedVaccineCode>
                <coding>
                    <code value="1240661000000107"/>
                    <display value="Severe acute respiratory syndrome coronavirus 2 vaccination contraindicated (situation)"/>
                    <system value="http://snomed.info/sct"/>
                </coding>
            </contraindicatedVaccineCode>
        </recommendation>
    </ImmunizationRecommendation>
</resource>
</entry>
```

### Equivalent HL7v3 coded entry
**Note:** Medication recommendations is not a supported Summary Care Record CRE Type. Non-supported SCR CRE Types use the "default" Clinical Observations and Findings CRE Type.

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
				<code code="1240661000000107" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Severe acute respiratory syndrome coronavirus 2 vaccination contraindicated (situation)">
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