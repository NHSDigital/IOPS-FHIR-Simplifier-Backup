#### Get SCR Document

This interaction returns the latest normal SCR. 

| Endpoint |
|--|
| https://[baseUrl]/Bundle |

| Parameters |
|--|
| document: uuid |
| patient: NHSNo |

| Query |
|--|
| GET https://[baseUrl]/Bundle?composition.identifier=[uuid]$composition.subject:Patient.identifier=https://fhir.nhs.uk/Id/nhs-number\|[nhsNo] |

Idiomatically, this says: get me the GP Summary with this identifier, for the patient with this NHS number

### Client view of Retrieve Latest SCR sequence diagram

{{render:getscrdocumentclient}}

### Example Get SCR Document call

```
GET https://[baseUrl]/Bundle?
 composition.identifier=[uuid]$
 composition.subject:Patient.identifier=https://fhir.nhs.uk/Id/nhs-number|9990001234
 /HTTP/1
```

### Example Get SCR Document response


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
        "resourceType": "Bundle",
        "id": "f61e545c-d52c-4b62-9668-3dcc6c27fc50",
        "identifier": {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "1ff370b6-fc5b-40a1-9721-2a942e301666"
        },
        "type": "document",
        "timestamp": "2007-03-15T01:00:00Z",
        "entry":  [
            {
                "fullUrl": "urn:uuid:2880eedf-76f0-4f38-9681-dc158e937da7",
                        "resource": {
                            "resourceType": "Composition",
                            "id": "2880eedf-76f0-4f38-9681-dc158e937da7",
                            "identifier": {
                                "system": "https://tools.ietf.org/html/rfc4122",
                                "value": "C058D90F-E526-4A27-A46E-E86229096AAC"
                            },
                            "status": "final",
                            "type": {
                                "coding":  [
                                    {
                                        "system": "http://snomed.info/sct",
                                        "code": "196981000000101",
                                        "display": "General Practice Summary"
                                    }
                                ]
                            },
                            "date": "2007-03-15T01:00:00Z",
                            "subject": {
                                "reference": "urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc"
                            },
                            "author":  [
                                {
                                    "reference": "urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106",
                                    "display": "Dr Steve Jones"
                                }
                            ],
                            "title": "General Practice Summary",
                            "section":  [
                                {
                                    "title": "General Practice Summary",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Allergies and Adverse Reactions",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Repeat Medication",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Acute Medication",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Discontinued Repeat Medication",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Risks to Care professional or Third Party",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Diagnoses",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Problems and issues",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Clinical Observation and Findings",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Treatments",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Investigations",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Provision of Advice and Information to Patients and Carers",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Personal Preferences",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Social and Personal Circumstances",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Services, Care Professionals and Carers",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Lifestyle",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                },
                                {
                                    "title": "Family History",
                                    "text": {
                                        "status": "generated",
                                        "comment": "--- We have skipped the narrative for better readability of the resource ---"
                                    }
                                }
                            ]
                        }
                    },
                    {
                        "fullUrl": "urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106",
                        "resource": {
                            "resourceType": "PractitionerRole",
                            "id": "83c26c8f-ee72-4534-8891-0136972b2106",
                            "identifier":  [
                                {
                                    "system": "http://fhir.nhs.net/Id/sds-role-profile-id",
                                    "value": "673836492727"
                                }
                            ],
                            "practitioner": {
                                "reference": "urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"
                            }
                        }
                    },
                    {
                        "fullUrl": "urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8",
                        "resource": {
                            "resourceType": "Practitioner",
                            "id": "b1a41ee5-b88b-4f66-bd83-24343bf63dd8",
                            "name":  [
                                {
                                    "family": "Jones",
                                    "given":  [
                                        "Steve"
                                    ],
                                    "prefix":  [
                                        "Dr"
                                    ]
                                }
                            ]
                        }
                    },
                    {
                        "fullUrl": "urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc",
                        "resource": {
                            "resourceType": "Patient",
                            "id": "b6f5dd89-fc3a-466d-baad-126c0aac46fc",
                            "identifier":  [
                                {
                                    "extension":  [
                                        {
                                            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1",
                                            "valueCodeableConcept": {
                                                "coding":  [
                                                    {
                                                        "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1",
                                                        "code": "01",
                                                        "display": "Number present and verified"
                                                    }
                                                ]
                                            }
                                        }
                                    ],
                                    "system": "https://fhir.nhs.uk/Id/nhs-number",
                                    "value": "9900004948"
                                }
                            ]
                        }
                    }
                ]
          },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```


### Spine view of Get SCR Document sequence diagram

{{render:getscrdocumentspine}}
