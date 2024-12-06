## {{page-title}}

```xml
<entry>
  <fullUrl value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0" />
  <resource>
    <Patient>
      <id value="1e2b5223-1cd8-43ff-8a67-55dec3edb9b0" />
      <meta>
        <profile value="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1" />
      </meta>
      <identifier>
        <extension
          url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
          <valueCodeableConcept>
            <coding>
              <system
                value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1" />
              <code value="01" />
              <display value="Number present and verified" />
            </coding>
          </valueCodeableConcept>
        </extension>
        <system value="https://fhir.nhs.uk/Id/nhs-number" />
        <value value="2378954317" />
      </identifier>
      <name>
        <use value="official" />
        <text value="Mr William Smith" />
        <family value="Smith" />
        <given value="William" />
        <prefix value="Mr" />
      </name>
      <telecom>
        <system value="phone" />
        <value value="01132789365" />
        <use value="home" />
      </telecom>
      <gender value="male" />
      <birthDate value="1956-02-04" />
      <address>
        <use value="home" />
        <type value="both" />
        <text value="14 Sunny Mews, Overtown, West Yorkshire, LS17 4NK" />
        <line value="14 Sunny Mews" />
        <city value="Overtown" />
        <district value="West Yorkshire" />
        <postalCode value="LS17 4NK" />
      </address>
      <maritalStatus>
        <coding>
          <system value="http://hl7.org/fhir/v3/MaritalStatus" />
          <code value="M" />
          <display value="Married" />
        </coding>
      </maritalStatus>
      <contact>
        <relationship>
          <coding>
            <system value="http://hl7.org/fhir/v2/0131" />
            <code value="N" />
            <display value="Next-of-Kin" />
          </coding>
        </relationship>
        <name>
          <use value="official" />
          <family value="Smith" />
          <given value="June" />
        </name>
        <telecom>
          <system value="phone" />
          <value value="01132789365" />
        </telecom>
        <gender value="female" />
      </contact>
      <generalPractitioner>
        <reference value="urn:uuid:33cd4a2a-417f-4449-8293-31b15ea37470" />
      </generalPractitioner>
      <managingOrganization>
        <reference value="urn:uuid:e46d86bf-1720-4c55-878f-a034d8349bbd" />
      </managingOrganization>
    </Patient>
  </resource>
</entry>
```