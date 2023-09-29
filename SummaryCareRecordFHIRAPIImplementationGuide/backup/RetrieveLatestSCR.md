#### Retrieve Latest SCR

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This interaction is deprecated. Client systems should use the <a href="http://simplifier.net/guide/summarycarerecordwithcodeddata/getscrid">Get SCR Id</a> and <a href="http://simplifier.net/guide/summarycarerecordwithcodeddata/getscrdocument">Get SCR Document</a> interactions instead.</div>

This interaction returns the latest normal SCR. It is intended for clients which don't have local GP Summaries available e.g. in an Ambulance SCR client app.

| Endpoint |
|--|
| https://[baseURL]/DocumentReference |

| Parameters |
|--|
| patient: NHSNo |

### Client view of Retrieve Latest SCR sequence diagram

{{render:retrieveclient}}

### Example Retrieve Latest SCR call

```
GET https://[baseURL]/DocumentReference?
 patient=9990001234
 /HTTP/1
```

### Example Retrieve Latest SCR response

Supplying the client with latest version

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
    " a Bundled Retrieve DocumentRef with in-lined latest SCR placeholder "
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


### Spine view of Retrieve Latest SCR sequence diagram

{{render:retrievespine}}
