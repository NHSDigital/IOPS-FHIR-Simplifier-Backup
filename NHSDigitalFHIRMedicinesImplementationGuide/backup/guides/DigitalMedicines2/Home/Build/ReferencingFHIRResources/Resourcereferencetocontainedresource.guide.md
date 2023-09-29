### Resource reference to contained resource

This **SHOULD NOT** be used as an alternative to FHIR RESTful API using resources. This should only be used when the resource is not complete, for example only the name of the patient or medication is known. 
This is not used in EPS.

The use of a contained FHIR resource should be the last option considered. The use of the `#` character.


```json
{
    "resourceType": "MedicationRequest",
    "contained": [
        {
            "resourceType": "Patient",
            "id": "1"
        },
        {
            "resourceType": "Medication",
            "id": "2"
        }
    ],
    "medicationReference": {
        "reference": "#2",
        "display": "Atenolol"
    },
    "subject": {
        "reference": "#1",
        "display": "Joe Bloggs"
    }
}
```