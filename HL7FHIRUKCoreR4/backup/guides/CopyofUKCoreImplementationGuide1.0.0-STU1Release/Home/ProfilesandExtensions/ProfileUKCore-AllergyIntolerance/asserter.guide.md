## `asserter`

The source of the information about the allergy. A reference to `patient`, `relatedPerson`, `practitioner` or `practitionerRole` resource.

### Provider Systems

Provider systems should provide at least the following minimum data within the referenced resource. 

`practioner`

- identifier
- name

`practionerRole`

- identifier
- practitioner (as above) OR organisation.identifier OR healthcareService.identifier

`patient`

- identifier:nhsNumber
- name

`relatedPerson`

- identifier
- name
- patient

Where a human asserter is not captured or cannot be confirmed, i.e. a `practioner`, `patient` or `relatedPerson`, the provider systems should reference an `Organisation` and/or `healthcareService` within a `PractitonerRole`, using the associated ODS code.

For example, asserted by "MILTON KEYNES UNIVERSITY HOSPITAL NHS FOUNDATION TRUST".

XML
``` xml
<PractitionerRole>
  <identifier>
   <value value="7d107ed2-70c6-43d9-9cbe-f19c319d1456"/>
  <organization>
    <identifier>
      <system value="https://fhir.nhs.uk/Id/ods-organization-code"/>
      <value value="RD8"/>
    </identifier>
    <display value="MILTON KEYNES UNIVERSITY HOSPITAL NHS FOUNDATION TRUST"/>
  </organization>
</PractitionerRole>
```

JSON
``` json
{
  "resource": {
    "resourceType": "PractitionerRole",
    "identifier": [
      {
        "value": "7d107ed2-70c6-43d9-9cbe-f19c319d1456"
      }
    ],
    "organization": {
      "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RD8"
      },
      "display": "MILTON KEYNES UNIVERSITY HOSPITAL NHS FOUNDATION TRUST"
    }
  }
}
```

### Consumer Systems

Consumer systems **MUST** consume this data.

---
