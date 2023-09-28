## `patient` (Mandatory)

A reference to the patient.

### Provider Systems

Provider systems **MUST** provide this data. 

Within a FHIR Messaging or FHIR Document implementation, include a **UKCore-Patient** resource within the Bundle with at least the minimum dataset populated as defined within the UK Core standard. The `reference` points to the resource in the Bundle.

XML
``` xml
<!-- within the AllergyIntolernce resource...-->
<patient>
  <reference value="urn:patient-011223344"/>
  <display value="Richard Smith"/>
</patient>
<!-- elsewhere in the Bundle...-->
  <Patient>
    <id value="urn:patient-011223344"/>
    <identifier>
      <system value="https://fhir.nhs.uk/Id/nhs-number"/>
      <value value="9912003888"/>
    </identifier>
    <name>
      <use value="official"/>
      <text value="Mr Richard Smith"/>
      <family value="Smith/>
      <given value="Richard/>
      <prefix value="Mr"/>
    </name>
    <gender value="male"/>
    <birthDate value="1956-02-04"/>>
  </Patient>

```

JSON
``` json
// within the AllergyIntolernce resource...

  "patient": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith",
  }

// elsewhere in the Bundle...


  {
    "fullUrl": "urn:patient-011223344",
    "resource": {
      "resourceType": "Patient",
      "id": "urn:patient-011223344",
      "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9912003888"
      },
      "name": {
        "use": "official",
        "text": "Mr Richard Smith",
        "family": "Smith",
        "given": "Richard",
        "prefix": "Mr"
      },
      "gender": "male",
      "birthDate": "1956-02-04"
    }
  }
```

Within a RESTful implemementation a `reference` and/or `identifier` **MUST** be provided that allows the consumer system to query another API if they need to access the complete **UKCore-Patient** resource. The `reference` points to the resource in the Bundle.

For implementations within England and Wales, the `identifier` could be the patient's **NHS Number**, allowing consumer system to use the [NHS Digital Personal Demographics Service FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir) return a Patient resource.

XML
``` xml
<patient>
  <reference value="urn:patient-011223344"/>
  <display value="Richard Smith"/>
  <identifier>
    <system value="https://fhir.nhs.uk/Id/nhs-number"/>
    <value value="9912003888"/>
  </identifier>
</patient>
```

JSON
``` json
{
  "patient": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith",
    "identifier": {
      "system": "https://fhir.nhs.uk/Id/nhs-number",
      "value": "9912003888"
    }
  }
}
```

For implementations within Scotland, the `identifier` could be the patient's **CHI Number**.

XML
``` xml
<patient>
  <reference value="urn:patient-011223344"/>
  <display value="Richard Smith"/>
  <identifier>
    <system value="https://fhir.nhs.uk/Id/chi-number"/>
    <value value="0402568876"/>
  </identifier>
</patient>
```

JSON
``` json
{
  "patient": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith",
    "identifier": {
      "system": "https://fhir.nhs.uk/Id/chi-number",
      "value": "0402568876"
    }
  }
}
```

### Consumer Systems

Consumer systems **MUST** consume this data.

---
