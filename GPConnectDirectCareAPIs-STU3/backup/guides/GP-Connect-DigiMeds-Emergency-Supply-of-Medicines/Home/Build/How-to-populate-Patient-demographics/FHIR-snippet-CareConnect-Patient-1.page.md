## {{page-title}}

```xml
<entry>
    <resource>
        <Patient xmlns="http://hl7.org/fhir">
            <id value="4d0e5c7a-2f0a-4ce4-8ab2-35ec960b1a75" />
            <meta>
                <profile value="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1" />
            </meta>
            <identifier>
                <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
                    <valueCodeableConcept>
                        <coding>
                            <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1" />
                            <code value="01" />
                            <display value="Number present and verified" />
                        </coding>
                    </valueCodeableConcept>
                </extension>
                <system value="https://fhir.nhs.uk/Id/nhs-number" />
                <value value="9223344867" />
            </identifier>
            <name>
                <use value="official" />
                <family value="CHAPMAN" />
                <given value="GEORGE" />
            </name>
            <gender value="male" />
            <birthDate value="1976-08-22" />
            <address>
                <use value="home" />
                <postalCode value="SA2 8AN" />
            </address>
            <generalPractitioner>
                <reference value="urn:uuid:b5608427-b313-4c72-96e8-b2a8fb35ad31" />
            </generalPractitioner>
        </Patient>
    </resource>
</entry>
```