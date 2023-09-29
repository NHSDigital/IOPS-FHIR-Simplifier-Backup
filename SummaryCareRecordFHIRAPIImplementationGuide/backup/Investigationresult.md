#### Investigation result

### CRE Type 163141000000104 \| Investigation results - care record element (record artifact) (uses Observation)

```xml
<entry>
<fullUrl value="urn:uuid:001c858c-3e3d-4b58-be94-0f46c79d8bae"/>
<resource>
    <Observation>
        <id value="001c858c-3e3d-4b58-be94-0f46c79d8bae"/>
        <meta>
            <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        </meta>
        <status value="final"/>
        <code>
            <coding>
                <system value="http://snomed.info/sct"/>
                <code value="1322781000000102"/>
                <display value="Severe acute respiratory syndrome coronavirus 2 antigen detection result positive (finding)"/>
            </coding>
        </code>
        <effectiveDateTime value="2020-08-05"/>
    </Observation>
</resource>
</entry>
```

### Equivalent HL7v3 coded entry

```xml
 <pertinentInformation2 typeCode="PERT" inversionInd="false"
     contextConductionInd="true" negationInd="false">
    <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2"
      extension="CSAB_RM-NPfITUK10.pertinentInformation1" />
    <seperatableInd value="true" />
    <pertinentCREType classCode="CATEGORY" moodCode="EVN">
    <code code="163141000000104"                    codeSystem="2.16.840.1.113883.2.1.3.2.4.15"
displayName="Investigation Results" />
    <component typeCode="COMP" contextConductionInd="true">
        <templateId root="2.16.840.1.113883.2.1.3.2.4.18.2"
           extension="CSAB_RM-NPfITUK10.component" />
        <seperatableInd value="false" />
        <UKCT_MT144043UK02.Finding classCode="OBS" moodCode="EVN">
        <id root="3CDB62E6-EFEA-4036-9709-52AE7ED7D930" />
            <code code="1322781000000102"   codeSystem="2.16.840.1.113883.2.1.3.2.4.15"
displayName="Severe acute respiratory syndrome coronavirus 2 antigen detection result positive (finding)">
            </code>
            <statusCode code="active" />
            <effectiveTime>
                <low value="20200805" />
            </effectiveTime>
        </UKCT_MT144043UK02.Finding>
    </component>
    </pertinentCREType>
</pertinentInformation2>
```