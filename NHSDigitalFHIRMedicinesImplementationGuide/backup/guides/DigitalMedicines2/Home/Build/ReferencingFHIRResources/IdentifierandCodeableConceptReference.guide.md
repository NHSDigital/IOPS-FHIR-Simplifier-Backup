### Identifier and CodeableConcept Reference

Using references by identifier is the preferred option in FHIR Messaging (and EPS). This is focused on using codes from either NHS Data Dictionary or SNOMED CT.
It is recommended that the `reference.display` is populated with appropriate text as per the guidance within this document.

```json 
{
    "resourceType": "MedicationRequest",
    "medicationCodeableConcept": {
        "coding": [
            {
                "system": "http://snomed.info/sct",
                "code": "323465006",
                "display": "Flucloxacillin 500mg capsules"
            }
        ]
    },
    "subject": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "2245386903"
        },
        "display": "Joe Bloggs"
    }
}
```