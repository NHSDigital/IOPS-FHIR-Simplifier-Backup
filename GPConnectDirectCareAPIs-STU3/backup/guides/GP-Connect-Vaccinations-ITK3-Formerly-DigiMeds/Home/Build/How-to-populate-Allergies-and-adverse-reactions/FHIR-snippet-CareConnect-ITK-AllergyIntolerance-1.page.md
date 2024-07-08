## {{page-title}}

```xml
<entry>
    <fullUrl value="urn:uuid:07630115-9a30-4a2c-b78a-f9bd4a481dd2" />
    <resource>
        <AllergyIntolerance>
            <id value="07630115-9a30-4a2c-b78a-f9bd4a481dd2" />
            <meta>
                <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-AllergyIntolerance-1" />
            </meta>
            <identifier>
                <system value="EMISFHIRTesting-1530" />
                <value value="Scenario_4_Day 1_AR-1530_2" />
            </identifier>
            <clinicalStatus value="active" />
            <verificationStatus value="unconfirmed" />
            <type value="intolerance" />
                <code>
                <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="39326911000001101" />
                    <display value="COVID-19 mRNA (nucleoside modified) Vaccine Moderna 0.1mg/0.5mL dose dispersion for injection multidose vials (Moderna, Inc)" />
                </coding>
            </code>
            <patient>
                <reference value="urn:uuid:4d0e5c7a-2f0a-4ce4-8ab2-35ec960b1a75" />
                <display value="CHAPMAN, George" />
            </patient>
            <assertedDate value="2020-12-21" />
            <reaction>
                <manifestation>
                    <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="16514006" />
                    <display value="Moist skin (finding)" />
                    </coding>
                </manifestation>
                <description value="looked a bit damp" />
                <onset value="2020-12-21T00:00:00+00:00" />
                <severity value="severe" />
            </reaction>
        </AllergyIntolerance>
    </resource>
</entry>
```