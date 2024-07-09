## {{page-title}}

```xml
<entry>
    <fullUrl value="urn:uuid:05b2add4-c00d-47da-9035-399e3e8adb58" />
    <resource>
        <Immunization>
            <id value="05b2add4-c00d-47da-9035-399e3e8adb58" />
            <meta>
                <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-DM-Immunization-1" />
            </meta>
            <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DateRecorded-1">
                <valueDateTime value="2020-12-21T00:00:00+00:00" />
            </extension>
            <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-VaccinationProcedure-1">
                <valueCodeableConcept>
                    <coding>
                        <system value="http://snomed.info/sct" />
                        <code value="1324681000000101" />
                        <display value="Administration of first dose of SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccine" />
                    </coding>
                </valueCodeableConcept>
            </extension>
            <identifier>
                <system value="https://example.com/identifier/digital-medicines/vaccination" />
                <value value="foo" />
            </identifier>
            <status value="completed" />
            <notGiven value="false" />
            <vaccineCode>
                <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="39326911000001101" />
                    <display value="COVID-19 mRNA (nucleoside modified) Vaccine Moderna 0.1mg/0.5mL dose dispersion for injection multidose vials - Moderna, Inc" />
                </coding>
            </vaccineCode>
            <patient>
                <reference value="urn:uuid:4d0e5c7a-2f0a-4ce4-8ab2-35ec960b1a75" />
                <display value="CHAPMAN, George" />
            </patient>
            <encounter>
                <reference value="urn:uuid:a807d9eb-ab18-4f5e-a323-ef9c6efeff0c" />
            </encounter>
            <date value="2020-12-21T12:34:44+00:00" />
            <primarySource value="true" />
            <manufacturer>
                <reference value="urn:uuid:f653edb4-6de5-4eef-bab3-bc9ffadfe2e0" />
                <display value="Moderna" />
            </manufacturer>
            <lotNumber value="GH56565" />
            <expirationDate value="2020-12-22" />
            <site>
                <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="368208006" />
                    <display value="Left upper arm structure (body structure)" />
                </coding>
            </site>
            <route>
                <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="78421000" />
                    <display value="Intramuscular Route (qualifier value)" />
                </coding>
            </route>
            <doseQuantity>
                <value value="1" />
                <unit value="dose" />
                <system value="http://snomed.info/sct" />
                <code value="3317411000001100" />
            </doseQuantity>
            <practitioner>
                <role>
                    <coding>
                    <system value="http://hl7.org/fhir/v2/0443" />
                    <code value="AP" />
                    <display value="Administering Provider" />
                    </coding>
                </role>
                <actor>
                    <reference value="urn:uuid:8dffa561-2481-490a-b24a-0b6f65dc814e" />
                </actor>
            </practitioner>
            <explanation>
                <reason>
                    <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="443684005" />
                    <display value="Disease outbreak (event)" />
                    </coding>
                </reason>
            </explanation>
        </Immunization>
    </resource>
</entry>
```