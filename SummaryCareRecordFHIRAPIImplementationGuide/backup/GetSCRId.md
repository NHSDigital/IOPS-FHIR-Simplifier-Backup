#### Get SCR Id


This interaction returns the universally unique identifier (UUID) of the latest version GP Summary held for the patient.

| Endpoint |
|--|
| https://[baseURL]/DocumentReference |



| Parameters |
|--|
| patient: NHSNo |

| Query |
|--|
| GET https://[baseUrl]/DocumentReference?patient=https://fhir.nhs.uk/Id/nhs-number\|[nhsNo]&type=http://snomed.info/sct\|196981000000101&_sort=date&_count=1 |

Idiomatically, this says: get me the pointer to the latest GP Summary

### Client view of Get SCR Id sequence diagram

{{render:getscridclient}}

### Example Get SCR Id call


```
GET https://[baseURL]/DocumentReference?
 patient=https://fhir.nhs.uk/Id/nhs-number|9990001234&
 &type=http://snomed.info/sct|196981000000101&
 _sort=date&
 _count=1
 /HTTP/1
```

### Example Get SCR Id response

Returns a DocumentReference pointer to the latest GP Summary document.

```
HTTP/1.1 200 OK
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```

```json
{
  "resourceType": "Bundle",
  "id": "78caaa2e-8cfc-4588-aaa3-52efbbf32845",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "fullUrl": "https://[baseURL]/DocumentReference/fa7eafcd-1294-433e-ab46-4db95b58635c",
      "resource": {
        "resourceType": "DocumentReference",
        "id": "fa7eafcd-1294-433e-ab46-4db95b58635c",
        "masterIdentifier": {
          "system": "https://fhir.nhs.uk/Id/nhsSCRUUID",
          "value": "C058D90F-E526-4A27-A46E-E86229096AAC"
        },
        "status": "current",
        "type": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "196981000000101",
              "display": " General Practice Summary"
            }
          ]
        },
        "subject": {
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9990001234"
          }
        },
        "securityLabel": [
          {
            "coding": [
              {
              "system": "https://fhir.nhs.uk/CodeSystem/SCR-ACSPermission",
              "code": "Ask"
              }
            ]
          }
        ],
        "content": [
          {
            "attachment": {
              "url": "https://[baseUrl]/Bundle?composition.identifier=C058D90F-E526-4A27-A46E-E86229096AAC$composition.subject:Patient.identifier=https://fhir.nhs.uk/Id/nhs-number|9990001234"
            }
          }
        ],
        "context": {
          "event": [
            {
              "coding": [
                {
                "system": "http://snomed.info/sct",
                "code": "196981000000101",
                "display": " General Practice Summary"
                }
              ]
            }
          ]
        }
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```


### Spine view of Verify Latest SCR sequence diagram

{{render:getscridspine}}