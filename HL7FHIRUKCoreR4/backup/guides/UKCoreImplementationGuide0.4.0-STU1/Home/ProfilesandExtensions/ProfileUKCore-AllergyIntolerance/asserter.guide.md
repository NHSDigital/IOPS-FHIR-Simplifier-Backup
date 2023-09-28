## `asserter`

A reference to the source of the information about the allergy. The resource being referenced should conform to one of the following:

- {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}
- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}
- {{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}

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
