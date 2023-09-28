## {{page-title}}

The adoption of a common GET API syntax to read a specific resource or search a FHIR server would allow the same software to, for example, read a FHIR resource from a GP system or read a FHIR resource from shared records service. The query syntax can be the same for both use cases (or workflows), using a different base URL technical end-point.

### GET by 'identifier'

To query a FHIR server for a specific resource by identifier;

```
GET [base]/{resource}?identifier={value}
```

For example;

```
GET https://myfhirserver.net/AllergyIntolerance?identifier=a54219b8-f741-4c47-b662-e4f8dfa49ab6
```

### GET by 'identifier', such as NHS Number

To query a FHIR server for a specific resources for a given patient;

```
GET [base]/{resource}?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|{NHS_Number}
```

For example;

```
GET https://myfhirserver.net/AllergyIntolerance?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254
```

### Search Results

Refer to the {{pagelink:Examples-Index}} in this implementation guidance.

---
