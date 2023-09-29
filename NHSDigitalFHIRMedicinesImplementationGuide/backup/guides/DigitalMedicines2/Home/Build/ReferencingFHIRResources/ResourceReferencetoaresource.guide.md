### Resource Reference to a resource

FHIR Message Bundles should be self contained and they should not require an external FHIR Server to process the message. In these cases referenced resources should be contained in the Bundle. It is suggested to use UUID references to navigate the resources in the Bundle, mainly to distinguish between resources within the Bundle and externally referenced resources.

```json
{
    "resourceType": "Bundle",
    "entry": [
        {
            "fullUrl": "urn:uuid:5fe0dde7-2cdc-43c1-b346-11dda63b51d2",
            "resource": {
                "resourceType": "Patient",
                "id": "2245386903"
            }
        },
        {
            "fullUrl": "urn:uuid:3e2097b7-3b28-4954-bded-d6af82a10c40",
            "resource": {
                "resourceType": "Medication",
                "id": "87652004",
                "code": {
                    "coding": [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "87652004",
                            "display": "Atenolol"
                        }
                    ]
                }
            }
        },
        {
            "resource": {
                "resourceType": "MedicationRequest",
                "medicationReference": {
                    "reference": "urn:uuid:3e2097b7-3b28-4954-bded-d6af82a10c40",
                    "display": "Atenolol"
                },
                "subject": {
                    "reference": "urn:uuid:5fe0dde7-2cdc-43c1-b346-11dda63b51d2",
                    "display": "Joe Bloggs"
                }
            }
        }
    ]
}
```

Within EPS the preference is to move to identifier references as this provides the key information a consumer requires. This also avoids large messages exchanging a considerable amount of reference data. The exception to this is likely to be the `Patient` resource which will normally be included in the FHIR Message Bundle.

FHIR RESTful API's may make references to resources held on FHIR Servers. 

```json

{
    "resourceType": "MedicationRequest",
    "medicationReference": {
        "reference": "https://fhir.midyorks.nhs.uk/Medication/87652004",
        "display": "Atenolol"
    },
    "subject": {
        "reference": "https://fhir.midyorks.nhs.uk/Patient/2245386903",
        "display": "Joe Bloggs"
    }
}

```

Not the use of `baseUrl` / `resource` / `resource.id`. Local references, i.e. referencing a resource on the same server, may omit the `baseUrl`.

```json
{
    "resourceType": "MedicationRequest",
    "medicationReference": {
        "reference": "Medication/87652004",
        "display": "Atenolol"
    },
    "subject": {
        "reference": "Patient/2245386903",
        "display": "Joe Bloggs"
    }
}

```
