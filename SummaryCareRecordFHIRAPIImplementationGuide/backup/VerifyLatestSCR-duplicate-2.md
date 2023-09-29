#### Verify Latest SCR

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This interaction is deprecated. Client systems should use the <a href="http://simplifier.net/guide/summarycarerecordwithcodeddata/getscrid">Get SCR Id</a> and <a href="http://simplifier.net/guide/summarycarerecordwithcodeddata/getscrdocument">Get SCR Document</a> interactions instead.</div>


This interaction verifies that the locally held SCR is the latest normal version. If it is not, the interaction returns the latest version. This is the main interaction for GP systems, as the calling client system is very likely to already hold the latest SCR.

| Endpoint |
|--|
| https://[baseURL]/DocumentReference |

### DQ - what is the baseURL for the SCR FHIR API?

| Parameters |
|--|
| patient: NHSNo |
| identifier: UUID of latest SCR for patient on calling system |

| Requirement |
|--|
| GP systems SHALL supply their latest SCR UUID as a query parameter, so that the majority of calls verify the SCR is the latest normal version and API traffic is minimised |

### DN - Assume we're working in JSON

### Client view of Verify Latest SCR sequence diagram

{{render:verifyclient}}

### Example Verify Latest SCR call

Verify UUID matches latest on Spine
```
GET https://[baseURL]/DocumentReference?
 patient=9990001234&
 identifier=C058D90F-E526-4A27-A46E-E86229096AA
 /HTTP/1
```

### Example Verify Latest SCR response - Confirm Latest

Confirming that client has latest normal version

```
HTTP/1.1 200 OK
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```

```
{
  "resourceType": "Bundle",
  "id": "78caaa2e-8cfc-4588-aaa3-52efbbf32845",
  "fhir_comments": [
    " a Bundled Verify DocumentRef with confirm latest SCR "
  ],
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "fullUrl": "https://[baseURL]/DocumentReference/fa7eafcd-1294-433e-ab46-4db95b58635c",
      "resource": {
        "resourceType": "DocumentReference",
        "id": "fa7eafcd-1294-433e-ab46-4db95b58635c",
        "_id": {
          "fhir_comments": [
            " logical id of this DocumentReference instance "
          ]
        },
        "masterIdentifier": {
          "fhir_comments": [
            " identifier GUID for the SCR latest instance (needs a namingSystem(s) or is it just urn:uuid?) "
          ],
          "system": "https://fhir.nhs.uk/Id/nhsSCRUUID",
          "value": "C058D90F-E526-4A27-A46E-E86229096AAC",
          "_value": {
            "fhir_comments": [
              " Do we care about case here? "
            ]
          }
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
        "content": [
          {
            "attachment": {
              "url": "https://[baseURL]/DocumentReference?patient=9990001234",
              "_url": {
                "fhir_comments": [
                  " url points to the Retrieve Latest SCR endpoint with constructed patient search parameter"
                ]
              }
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

### Example Verify Latest SCR response - Not Latest

Supplying the client with latest normal version

```
HTTP/1.1 200 OK
Date: Tue, 24 Aug 2020 11:00:00 GMT
Content-Type: application/fhir+json
```

```
{
  "resourceType": "Bundle",
  "id": "78caaa2e-8cfc-4588-aaa3-52efbbf32845",
  "fhir_comments": [
    " a Bundled Verify DocumentRef with in-lined latest SCR placeholder "
  ],
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "fullUrl": "https://[baseURL]/DocumentReference/fa7eafcd-1294-433e-ab46-4db95b58635c",
      "resource": {
        "resourceType": "DocumentReference",
        "id": "fa7eafcd-1294-433e-ab46-4db95b58635c",
        "_id": {
          "fhir_comments": [
            " logical id of this DocumentReference instance "
          ]
        },
        "masterIdentifier": {
          "fhir_comments": [
            " identifier GUID for the SCR latest instance (needs a namingSystem(s) or is it just urn:uuid?) "
          ],
          "system": "https://fhir.nhs.uk/Id/nhsSCRUUID",
          "value": "C058D90F-E526-4A27-A46E-E86229096AAC",
          "_value": {
            "fhir_comments": [
              " Do we care about case here? "
            ]
          }
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
        "content": [
          {
            "attachment": {
              "contentType": "application/fhir+json",
              "_contentType": {
                "fhir_comments": [
                  " contentType MUST hold the Mime type of any in-lined data"
                ]
              },
              "data": "[large base64encoded binary representation of the latest SCR FHIR Document]",
              "title": "GP Summary",
              "creation": "2020-08-20T16:00:00+00:00"
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

{{render:verifyspine}}
