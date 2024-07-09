## {{page-title}}

```xml
<entry>
    <fullUrl value="urn:uuid:0b8a397b-4e7e-4297-a1dd-f75bec62b247" />
    <resource>
        <AllergyIntolerance>
            <id value="0b8a397b-4e7e-4297-a1dd-f75bec62b247" />
            <meta>
                <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-AllergyIntolerance-1" />
            </meta>
            <identifier>
                <system value="https://example.com/identifier/digital-medicines/vaccination" />
                <value value="foo" />
            </identifier>
            <clinicalStatus value="active" />
            <verificationStatus value="unconfirmed" />
            <type value="allergy" />
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
                    <code value="404640003" />
                    <display value="Dizziness (finding)" />
                </coding>
            </manifestation>
            <description value="described feeling all whoozy" />
            <onset value="2020-12-21T00:00:00+00:00" />
            <severity value="mild" />
            </reaction>
        </AllergyIntolerance>
    </resource>
</entry>
<entry>
    <fullUrl value="urn:uuid:07630115-9a30-4a2c-b78a-f9bd4a481dd2" />
    <resource>
        <AllergyIntolerance>
            <id value="07630115-9a30-4a2c-b78a-f9bd4a481dd2" />
            <meta>
                <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-AllergyIntolerance-1" />
            </meta>
            <identifier>
                <system value="https://example.com/identifier/digital-medicines/vaccination" />
                <value value="bar" />
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