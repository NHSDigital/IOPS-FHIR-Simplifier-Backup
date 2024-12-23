## {{page-title}}

### Allergic to Paracetamol
An example using an Actual Medicinal Product (AMP).

```xml
<AllergyIntolerance>
    <id value="e5e02a1b-098b-45de-812b-22586128d341"/>
    <meta>
        <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-AllergyIntolerance-1"/>
    </meta>
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122"/>
        <value value="262335c0-6ddd-4a1c-8409-e6bbcc230ee0"/>
    </identifier>
    <clinicalStatus value="active"/>
    <verificationStatus value="confirmed"/>
    <code>
        <coding>
            <system value="http://snomed.info/sct"/>
            <code value="382911000001102"/>
            <!--Added by chbe -->
            <display value="Paracetamol 500mg tablets (A A H Pharmaceuticals Ltd)"/>
        </coding>
    </code>
    <patient>
        <reference value="urn:uuid:e82a6a10-7409-4bc1-8f00-ec577ab1f7a8"/>
        <display value="SYKES, Ray"/>
    </patient>
    <assertedDate value="2020-05-31T21:53:00+01:00"/>
</AllergyIntolerance>
```

### No known drug allergy

```xml
<AllergyIntolerance xmlns="http://hl7.org/fhir">
    <id value="d31bba78-4ae4-450c-9a5e-c6b33723dedb"/>
    <meta>
        <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-AllergyIntolerance-1"/>
    </meta>
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122"/>
        <value value="d31bba78-4ae4-450c-9a5e-c6b33723dedb"/>
    </identifier>
    <clinicalStatus value="active"/>
    <verificationStatus value="unconfirmed"/>
    <category value="medication"/>
    <code>
        <coding>
            <system value="http://snomed.info/sct"/>
            <code value="409137002"/>
            <display value="No known drug allergy"/>
        </coding>
    </code>
    <patient>
        <reference value="urn:uuid:1ca429f3-6d18-42a4-9de9-b58eaed77c7f"/>
        <display value="THYME, Justin"/>
    </patient>
    <assertedDate value="2020-06-22T16:25:28Z"/>
</AllergyIntolerance>
````