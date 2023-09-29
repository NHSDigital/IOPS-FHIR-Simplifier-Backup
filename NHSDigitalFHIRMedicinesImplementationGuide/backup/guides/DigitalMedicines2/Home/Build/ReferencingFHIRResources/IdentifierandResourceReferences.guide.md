### Identifier and Resource References

The two approaches to referencing can be used together. E.g.

An identifier reference such as 

```json
{
    "resourceType": "MedicationRequest",
    "subject": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "2245386903"
        },
        "display": "Joe Bloggs"
    }
}
```
can be combined with a resource reference

```json

{
    "resourceType": "MedicationRequest",
    "subject": {
        "reference": "https://fhir.midyorks.nhs.uk/Patient/2245386903",
        "display": "Joe Bloggs"
    }
}

```

Resulting in this example

```json

{
    "resourceType": "MedicationRequest",
    "subject": {
        "reference": "https://fhir.midyorks.nhs.uk/Patient/2245386903",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "2245386903"
        },
        "display": "Joe Bloggs"
    }
}

```

In this example a receiving system has a choice. 

If NHS Number and patient name is sufficient they can process the MedicationRequest without any further API calls or have to resolve the reference within the Bundle.

If they need more Patient details, they can either follow the reference 
`https://fhir.midyorks.nhs.uk/Patient/2245386903`, or use the NHS Number to query a local such as PAS/MPI or Patient Demographic Service(PDS).


