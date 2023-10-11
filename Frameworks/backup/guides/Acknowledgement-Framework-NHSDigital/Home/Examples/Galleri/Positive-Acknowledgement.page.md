## {{page-title}}

### Positive Acknowledgement of Appointment

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send appointment
nhsenglandgps --> grailuk: Send positive acknowledgement
</plantuml>

<br /><br />
## An Example to Send Appointment

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1c}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1c}}
</div>


<br /><br />
#### An Example to Receive positive acknowledgement response

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json: }}
</div>

### Positive Acknowledgement of Test Report (Cancer Markers Detected)

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send test report with cancer markers detected
nhsenglandgps --> grailuk: Send positive acknowledgement
</plantuml>

<br /><br />
#### Message 1 - Send test report (cancer markers detected)
```json
{
    "resourceType": "Bundle",
    "id": "f862ec24-e05a-42d1-aea5-d0a9c092e6ae",
    "meta": {
        "lastUpdated": "2020-09-20T10:22:00+00:00"
    },
    "identifier": {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "f36927ef-7703-45ed-b0e5-6ec6723cf0f6"
    },
    "type": "message",
    "entry":  [
        {
            "fullUrl": "urn:uuid:a4409d7c-b613-477c-b623-87e60406c2f0",
            "resource": {
                "resourceType": "MessageHeader",
                "id": "a4409d7c-b613-477c-b623-87e60406c2f0",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader"
                    ]
                },
                "eventCoding": {
                    "system": "TBD",
                    "code": "TBD",
                    "display": "TBD"
                },
                "destination":  [
                    {
                        "name": "Executive Agency - NHS ENGLAND - X26",
                        "endpoint": "${NhsMeshMailboxId}",
                        "receiver": {
                            "reference": "urn:uuid:bf7a76d3-5b44-4194-a9e0-d1cc1ea5e50e"
                        }
                    }
                ],
                "sender": {
                    "reference": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e"
                },
                "source": {
                    "endpoint": "${GrailMeshMailboxId}"
                },
                "focus":  [
                    {
                        "reference": "urn:uuid:3d2f37fd-ca19-4199-9f72-4871cfe12df1"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e",
            "resource": {
                "resourceType": "Organization",
                "id": "d6407de7-0e86-45eb-93cb-035094aaa49e",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "8KG14"
                    }
                ],
                "name": "GRAIL BIO UK LTD",
                "address":  [
                    {
                        "text": "TBD"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:e78b5421-8d55-4f61-8cbf-bee1c69513f1",
            "resource": {
                "resourceType": "Organization",
                "id": "e78b5421-8d55-4f61-8cbf-bee1c69513f1",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization"
                    ]
                },
                "identifier":  [
                    {
                        "system": "http://terminology.hl7.org/NamingSystem/CLIA",
                        "value": "${lab.cliaId} 34D2231294"
                    },
                    {
                        "system": "http://terminology.hl7.org/NamingSystem/CAP",
                        "value": "${lab.cap} GRAIL6793"
                    }
                ],
                "name": "${lab.name} GRAIL, LLC",
                "telecom":  [
                    {
                        "system": "phone",
                        "value": "+18336942553"
                    },
                    {
                        "system": "fax",
                        "value": "+16509999000"
                    },
                    {
                        "system": "email",
                        "value": "customerservice@grail.com"
                    }
                ],
                "address":  [
                    {
                        "text": "${lab.name}GRAIL RTP, ${lab.location} 4001 E NC 54 Hwy Assembly, Suite 1100"
                    }
                ],
                "contact":  [
                    {
                        "name": {
                            "text": "Ms Lab DIRECTOR"
                        }
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:bf7a76d3-5b44-4194-a9e0-d1cc1ea5e50e",
            "resource": {
                "resourceType": "Organization",
                "id": "bf7a76d3-5b44-4194-a9e0-d1cc1ea5e50e",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "X26"
                    }
                ],
                "name": "Executive Agency - NHS ENGLAND - X26",
                "address":  [
                    {
                        "line":  [
                            "THE LEEDS GOVERNMENT HUB",
                            "7-8 WELLINGTON PLACE"
                        ],
                        "city": "LEEDS",
                        "district": "WEST YORKSHIRE",
                        "postalCode": "LS1 4AP"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:f25e9d63-6a4e-4de6-b9dc-c912fda62b01",
            "resource": {
                "resourceType": "Practitioner",
                "id": "f25e9d63-6a4e-4de6-b9dc-c912fda62b01",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://fhir.nhs.uk/Id/sds-user-id",
                        "value": "3415870223"
                    }
                ],
                "name":  [
                    {
                        "text": "${orderingProvider.fullName} Prof Peter Johnson",
                        "suffix":  [
                            "${orderingProvider.credentials} CBE"
                        ]
                    }
                ],
                "address":  [
                    {
                        "text": "NHS England, Wellington House, 133-155 Waterloo Road, London, SE1 8UG, UK"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
            "resource": {
                "resourceType": "Patient",
                "id": "8d6c2cd5-0eec-496a-88d0-3785a135df09",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://grail.com/patient-id",
                        "value": "NHS-AB12-CD34"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:d9df1431-22ac-462a-946a-f195f6c639af",
            "resource": {
                "resourceType": "ServiceRequest",
                "id": "d9df1431-22ac-462a-946a-f195f6c639af",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest"
                    ]
                },
                "identifier":  [
                    {
                        "system": "http://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "status": "active",
                "intent": "order",
                "code": {
                    "coding":  [
                        {
                            "system": "TBD",
                            "code": "TBD",
                            "display": "TBD"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "requester": {
                    "reference": "urn:uuid:f25e9d63-6a4e-4de6-b9dc-c912fda62b01",
                    "display": "Peter Johnson"
                },
                "performer":  [
                    {
                        "reference": "urn:uuid:e78b5421-8d55-4f61-8cbf-bee1c69513f1",
                        "display": "GRAIL RTP"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:3d2f37fd-ca19-4199-9f72-4871cfe12df1",
            "resource": {
                "resourceType": "DiagnosticReport",
                "id": "3d2f37fd-ca19-4199-9f72-4871cfe12df1",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport"
                    ]
                },
                "basedOn":  [
                    {
                        "reference": "urn:uuid:d9df1431-22ac-462a-946a-f195f6c639af"
                    }
                ],
                "status": "final",
                "code": {
                    "coding":  [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "TBD",
                            "display": "TBD"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "issued": "2020-09-25T16:00:00+00:00",
                "performer":  [
                    {
                        "reference": "urn:uuid:e78b5421-8d55-4f61-8cbf-bee1c69513f1",
                        "display": "GRAIL RTP"
                    }
                ],
                "specimen":  [
                    {
                        "reference": "urn:uuid:756a8361-79ce-4561-afcb-a91fe19df123",
                        "display": "ABC12345689"
                    }
                ],
                "result":  [
                    {
                        "reference": "urn:uuid:9f7babcd-19cb-4063-b96b-61a20b2e07e6"
                    }
                ],
                "conclusion": "The Galleri test results report PDF document is the official source of the test result and contains important information regarding the Galleri test and the patient's test results. Please read the official report for complete results.",
                "presentedForm":  [
                    {
                        "contentType": "application/pdf",
                        "data": "VGhlIEdSQUlMIFBERiBnb2VzIGhlcmU="
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:9f7babcd-19cb-4063-b96b-61a20b2e07e6",
            "resource": {
                "resourceType": "Observation",
                "id": "9f7babcd-19cb-4063-b96b-61a20b2e07e6",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "status": "final",
                "code": {
                    "coding":  [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "TBD",
                            "display": "TBD"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "issued": "2020-09-25T16:00:00+00:00",
                "performer":  [
                    {
                        "reference": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e",
                        "display": "GRAIL RTP"
                    }
                ],
                "note":  [
                    {
                        "text": "${testResult.labComments}"
                    }
                ],
                "specimen": {
                    "reference": "urn:uuid:756a8361-79ce-4561-afcb-a91fe19df123"
                },
                "hasMember":  [
                    {
                        "reference": "urn:uuid:efae5859-28df-4e7d-be91-6df56d8215e4"
                    },
                    {
                        "reference": "urn:uuid:dacb177a-9501-4dcc-8b22-b941791ae0db"
                    },
                    {
                        "reference": "urn:uuid:3f9730c8-5527-4f58-9865-55aef4dfa11f"
                    }
                ]
            }
        },
        {
            "fullUrl": "urn:uuid:efae5859-28df-4e7d-be91-6df56d8215e4",
            "resource": {
                "resourceType": "Observation",
                "id": "efae5859-28df-4e7d-be91-6df56d8215e4",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "basedOn":  [
                    {
                        "reference": "urn:uuid:d9df1431-22ac-462a-946a-f195f6c639af"
                    }
                ],
                "status": "final",
                "code": {
                    "coding":  [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "TBD",
                            "display": "TBD"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "issued": "2020-09-25T16:00:00+00:00",
                "performer":  [
                    {
                        "reference": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e",
                        "display": "GRAIL RTP"
                    }
                ],
                "valueCodeableConcept": {
                    "coding":  [
                        {
                            "system": "https://grail.com/test-result",
                            "code": "CANCER_SIGNAL_DETECTED",
                            "display": "Cancer signal detected"
                        }
                    ]
                },
                "specimen": {
                    "reference": "urn:uuid:756a8361-79ce-4561-afcb-a91fe19df123"
                }
            }
        },
        {
            "fullUrl": "urn:uuid:dacb177a-9501-4dcc-8b22-b941791ae0db",
            "resource": {
                "resourceType": "Observation",
                "id": "dacb177a-9501-4dcc-8b22-b941791ae0db",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "status": "final",
                "code": {
                    "coding":  [
                        {
                            "system": "https://grail.com/cso-ordinal",
                            "code": "PRIMARY",
                            "display": "<analysis name> cancer signal predicted primary site"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "effectiveDateTime": "2019-01-29T16:00:00+00:00",
                "performer":  [
                    {
                        "reference": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e",
                        "display": "GRAIL RTP"
                    }
                ],
                "bodySite": {
                    "coding":  [
                        {
                            "system": "https://grail.com/cso-origin",
                            "code": "UPPER_GI",
                            "display": "Stomach, Oesophagus"
                        }
                    ]
                }
            }
        },
        {
            "fullUrl": "urn:uuid:3f9730c8-5527-4f58-9865-55aef4dfa11f",
            "resource": {
                "resourceType": "Observation",
                "id": "3f9730c8-5527-4f58-9865-55aef4dfa11f",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation"
                    ]
                },
                "identifier":  [
                    {
                        "system": "https://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "status": "final",
                "code": {
                    "coding":  [
                        {
                            "system": "https://grail.com/cso-ordinal",
                            "code": "SECONDARY",
                            "display": "analysis name cancer signal predicted secondary site (observable entity)"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "effectiveDateTime": "2019-01-29T16:00:00+00:00",
                "performer":  [
                    {
                        "reference": "urn:uuid:d6407de7-0e86-45eb-93cb-035094aaa49e",
                        "display": "GRAIL RTP"
                    }
                ],
                "bodySite": {
                    "coding":  [
                        {
                            "system": "https://grail.com/cso-origin",
                            "code": "PANCREAS_GALLBLADDER",
                            "display": "Pancreas, Gallbladder"
                        }
                    ]
                }
            }
        },
        {
            "fullUrl": "urn:uuid:756a8361-79ce-4561-afcb-a91fe19df123",
            "resource": {
                "resourceType": "Specimen",
                "id": "756a8361-79ce-4561-afcb-a91fe19df123",
                "meta": {
                    "profile":  [
                        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen"
                    ]
                },
                "identifier":  [
                    {
                        "system": "http://grail.com/grail-id",
                        "value": "${sample.orderingGrailId} NHS9123123"
                    }
                ],
                "status": "available",
                "type": {
                    "coding":  [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "119297000",
                            "display": "${sample.sampleType} Blood specimen"
                        }
                    ]
                },
                "subject": {
                    "reference": "urn:uuid:8d6c2cd5-0eec-496a-88d0-3785a135df09",
                    "display": "NHS-AB12-CD34"
                },
                "collection": {
                    "collectedDateTime": "2020-09-23T11:00:00+00:00"
                }
            }
        }
    ]
}
```
<br /><br />
#### Message 2 - Send positive acknowledgement
```json
{
  "resourceType": "Bundle",
  "type": "message",
  "entry": [
    {
      "fullUrl": "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader",
      "resource": {
        "resourceType": "MessageHeader",
        "eventCoding": {
          "system": "https://fhir.nhs.uk/CodeSystem/message-event",
          "code": "notification",
          "display": "Event Notification"
        },
        "destination": [
          {
            "name": "GRAIL (UK)",
            "endpoint": "https://uk.grail.com/api",
            "receiver": {
              "reference": "urn:uuid:ff09cccc-2c9b-4238-91d2-66fa6ee845c3",
              "display": "GRAIL (UK)"
            }
          }
        ],
        "source": {
          "name": "NHS England",
          "version": "0.0.5",
          "contact": {
            "system": "email",
            "value": "helpdesk@england.nhs.net"
          },
          "endpoint": "https://gps.digital.nhs.uk/api"
        },
        "response": {
          "identifier": "f862ec24-e05a-42d1-aea5-d0a9c092e6ae",
          "code": "ok"
        }
      }
    }
  ]
}