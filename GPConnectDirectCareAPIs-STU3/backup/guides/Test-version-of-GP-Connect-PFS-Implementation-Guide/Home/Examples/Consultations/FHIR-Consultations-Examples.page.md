## {{page-title}}

### Access Record Structured FHIR examples for Consultations.

### Request
Example of a call to return the following items from a patient's structured record:

* Consultations

#### Request payload

```json
{
   "resourceType": "Bundle",
   "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1"]},
   "id": "9b2482e8-97ef-49cd-9356-5768862fee89",
   "type": "collection",
   "entry":    [
      {"resource":       {
         "resourceType": "Patient",
         "id": "4d59c916-9726-11ec-af3f-0a58a9feac02",
         "meta":          {
            "versionId": "eb690329a472dd332bcdc3bd0acb5f16",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Patient-1"]
         },
         "extension":          [
                        {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-RegistrationDetails-1",
               "extension":                [
                                    {
                     "url": "registrationPeriod",
                     "valuePeriod":                      {
                        "start": "2022-02-26",
                        "end": "2023-12-08"
                     }
                  },
                                    {
                     "url": "registrationType",
                     "valueCodeableConcept": {"coding": [                     {
                        "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-RegistrationType-1",
                        "code": "T",
                        "display": "Temporary"
                     }]}
                  }
               ]
            },
                        {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-NHSCommunication-1",
               "extension":                [
                                    {
                     "url": "language",
                     "valueCodeableConcept": {"coding": [                     {
                        "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-HumanLanguage-1",
                        "code": "fr",
                        "display": "French"
                     }]}
                  },
                                    {
                     "url": "interpreterRequired",
                     "valueBoolean": true
                  }
               ]
            }
         ],
         "identifier": [         {
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-NHSNumberVerificationStatus-1",
               "valueCodeableConcept": {"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1",
                  "code": "01",
                  "display": "Number present and verified"
               }]}
            }],
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9693646525"
         }],
         "active": true,
         "name": [         {
            "use": "official",
            "family": "BAGGS",
            "prefix": ["MISS"],
            "given": ["Flora"]
         }],
         "telecom":          [
                        {
               "system": "phone",
               "value": "+441455290432",
               "use": "home"
            },
                        {
               "system": "phone",
               "value": "+447815123123",
               "use": "mobile"
            },
                        {
               "system": "phone",
               "value": "+442031231234",
               "use": "work"
            },
                        {
               "system": "email",
               "value": "patient1@gmail.com",
               "use": "home"
            }
         ],
         "gender": "female",
         "birthDate": "1971-07-09",
         "address": [         {
            "use": "home",
            "line":             [
               "1 Main St",
               "Villagey"
            ],
            "city": "Leicester",
            "district": "Leicestershire",
            "postalCode": "LE1 1AA",
            "country": "GBR"
         }],
         "contact": [         {
            "relationship":             [
               {"text": "brother"},
               {"text": "Next of kin"}
            ],
            "name":             {
               "use": "official",
               "text": "Fred Bloggs"
            }
         }],
         "managingOrganization": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "N82090",
         "meta":          {
            "versionId": "0ee3a2e01efdc6841424aee9a0640395",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "N82090"
         }],
         "active": true,
         "name": "Green Lane Medical Centre",
         "address": [         {
            "use": "work",
            "line": ["1 Main St"],
            "city": "London",
            "postalCode": "W1A 1AA",
            "country": "GBR"
         }],
         "telecom":          [
                        {
               "system": "phone",
               "value": "+442071231234",
               "use": "work"
            },
                        {
               "system": "fax",
               "value": "+442071231235",
               "use": "work"
            },
                        {
               "system": "email",
               "value": "gp.connect.test.site@medicus.health",
               "use": "work"
            }
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "8dbadb3a-a634-11ed-af2e-0adb7c23cfe0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/fd93c950a100235b81ca5e557e5b3fe9"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/78f405fe-a9c9-11ec-a0ff-0a58a9feac02"}
            }
         ],
         "period": {"start": "2023-02-01T15:39:00+00:00"},
         "serviceProvider": {"reference": "Organization/AX8X"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "78f405fe-a9c9-11ec-a0ff-0a58a9feac02",
         "meta":          {
            "versionId": "fcbc84d5285490f73a308bcbe0dd0270",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Prem Anandan",
            "family": "Prem Anandan"
         }]
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "fd93c950a100235b81ca5e557e5b3fe9",
         "meta":          {
            "versionId": "09dead7ad66cba62cfd19f0b9d09efa1",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "kledji ",
            "family": "kledji "
         }]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "AX8X",
         "meta":          {
            "versionId": "8d182720c50a4c5e42f8eecbdd1786cb",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "AX8X"
         }],
         "active": true,
         "name": "1 Diamond Home Care Ltd"
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8dbadb3a-a634-11ed-af2e-0adb7c23cfe0-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "date": "2023-02-06T15:54:23+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/8dc709dc-a634-11ed-bc27-0adb7c23cfe0"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8dc709dc-a634-11ed-bc27-0adb7c23cfe0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/e5225ff6-ec9e-11ec-b38a-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "date": "2023-02-06T15:40:16+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Heart disease",
         "entry":          [
            {"item": {"reference": "List/d860958e-a635-11ed-aeed-0a58a9feac02"}},
            {"item": {"reference": "List/e1429e18-a635-11ed-97ed-0a58a9feac02"}},
            {"item": {"reference": "List/ee198552-a635-11ed-bb11-0adb7c23cfe0"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d860958e-a635-11ed-aeed-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/df0d1240-a635-11ed-a297-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "df0d1240-a635-11ed-a297-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "df0d1240-a635-11ed-a297-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "22298006",
            "display": "Myocardial infarction",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "37443015"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Heart attack"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "effectiveDateTime": "2023-02-06",
         "issued": "2023-02-06T00:00:00+00:00",
         "performer":          [
            {"reference": "Practitioner/78f405fe-a9c9-11ec-a0ff-0a58a9feac02"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "e1429e18-a635-11ed-97ed-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/e9e8a03a-a635-11ed-85f8-0adb7c23cfe0"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "e9e8a03a-a635-11ed-85f8-0adb7c23cfe0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e9e8a03a-a635-11ed-85f8-0adb7c23cfe0"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "8655006",
            "display": "Lead measurement, quantitative, blood",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "132881000000116"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Blood lead level"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "effectiveDateTime": "2023-02-06",
         "issued": "2023-02-06T00:00:00+00:00",
         "performer":          [
            {"reference": "Practitioner/78f405fe-a9c9-11ec-a0ff-0a58a9feac02"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ee198552-a635-11ed-bb11-0adb7c23cfe0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Observation/f3b4148c-a635-11ed-a3d3-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "f3b4148c-a635-11ed-a3d3-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "f3b4148c-a635-11ed-a3d3-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "56265001",
            "display": "Heart disease",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "93561011"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"},
         "effectiveDateTime": "2023-02-06",
         "issued": "2023-02-06T00:00:00+00:00",
         "performer":          [
            {"reference": "Practitioner/78f405fe-a9c9-11ec-a0ff-0a58a9feac02"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "e5225ff6-ec9e-11ec-b38a-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "major"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "sibling"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/b69c2cfe-0817-11ed-90d9-069ffbeb8efa"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/df0d1240-a635-11ed-a297-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/e9e8a03a-a635-11ed-85f8-0adb7c23cfe0"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/f3b4148c-a635-11ed-a3d3-0a58a9feac02"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e5225ff6-ec9e-11ec-b38a-0a58a9feac02"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "414545008",
            "display": "Ischaemic heart disease",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "2537479013"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "IHD - Ischemic heart disease"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "assertedDate": "2022-06-15T12:32:53+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "bb1e3008-ba45-11ec-9b67-0a58a9feac02",
         "meta":          {
            "versionId": "acfbb3553175835c05b58346e1e8ed99",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": " Andrew Guiseley",
            "family": " Andrew Guiseley"
         }]
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "f057a9a8-ec9e-11ec-ab85-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "major"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "sibling"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/e5225ff6-ec9e-11ec-b38a-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "ReferralRequest/9ffa7590-06ab-11ed-95fc-0abc55c2c756"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "MedicationRequest/mr-d2ce54d8-3008-11ed-906c-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "DocumentReference/emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/4972df40-fb80-11ec-96b1-0656c2ef588e"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/c6cdec4a-fc67-11ec-9dc9-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "DocumentReference/emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/971117de-f90b-11ec-9c7d-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "ReferralRequest/13477f2a-f6e4-11ec-8765-0ad2cc072944"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/3ef6da7e-0df2-11ed-8354-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/1ccf7bc4-807d-11ed-963c-064380d115ae"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "f057a9a8-ec9e-11ec-ab85-0a58a9feac02"
         }],
         "clinicalStatus": "inactive",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "194828000",
            "display": "Angina pectoris",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "299755016"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Angina"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "abatementDateTime": "2022-12-22T00:00:00+00:00",
         "assertedDate": "2022-06-15T12:33:12+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "fe30e7b0-811d-11ed-825c-064380d115ae",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "fe30e7b0-811d-11ed-825c-064380d115ae"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-12-21T10:55:00+00:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "748dc0bc-9bbf-11ec-b043-0ae647c12c72",
         "meta":          {
            "versionId": "8e6c8a46904378c415be377c7e65737d",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Yogesh Mistry",
            "family": "Yogesh Mistry"
         }]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "fe30e7b0-811d-11ed-825c-064380d115ae-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/fe30e7b0-811d-11ed-825c-064380d115ae"},
         "date": "2022-12-21T10:56:21+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/fe3b0eac-811d-11ed-bae6-064380d115ae"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "fe3b0eac-811d-11ed-bae6-064380d115ae",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/fe30e7b0-811d-11ed-825c-064380d115ae"},
         "date": "2022-12-21T10:55:33+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "HF - Heart failure",
         "entry": [{"item": {"reference": "List/0a5cd292-811e-11ed-80bd-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "0a5cd292-811e-11ed-80bd-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/fe30e7b0-811d-11ed-825c-064380d115ae"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/114bcc3e-811e-11ed-8063-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "114bcc3e-811e-11ed-8063-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "114bcc3e-811e-11ed-8063-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/fe30e7b0-811d-11ed-825c-064380d115ae"},
         "effectiveDateTime": "2022-12-21",
         "issued": "2022-12-21T00:00:00+00:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "my notes "
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "ce17c772-6b26-11ed-807c-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ce17c772-6b26-11ed-807c-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-11-23T12:03:00+00:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "8b9d1140-9bbf-11ec-991d-0ae647c12c72",
         "meta":          {
            "versionId": "2e714249cff9cd996498c72a0809b2a7",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Martin Hillyard",
            "family": "Martin Hillyard"
         }]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ce17c772-6b26-11ed-807c-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ce17c772-6b26-11ed-807c-0a58a9feac02"},
         "date": "2022-11-23T12:06:42+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/ce1f23b4-6b26-11ed-b037-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ce1f23b4-6b26-11ed-b037-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ce17c772-6b26-11ed-807c-0a58a9feac02"},
         "date": "2022-11-23T12:03:12+00:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Topic 1",
         "entry": [{"item": {"reference": "List/d9d5d0a4-6b26-11ed-9d6f-0a0382d71aaa"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d9d5d0a4-6b26-11ed-9d6f-0a0382d71aaa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ce17c772-6b26-11ed-807c-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Evaluation",
         "entry": [{"item": {"reference": "Immunization/0052a54a-6b27-11ed-b999-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Immunization",
         "id": "0052a54a-6b27-11ed-b999-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Immunization-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DateRecorded-1",
               "valueDateTime": "2022-11-23T12:04:37+00:00"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-VaccinationProcedure-1",
               "valueCodeableConcept": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "247631000000101",
                  "display": "First pneumococcal conjugated vaccination",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "405281000000118"
                     }]
                  }]
               }]}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "0052a54a-6b27-11ed-b999-0a58a9feac02"
         }],
         "status": "completed",
         "notGiven": false,
         "vaccineCode": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "35111211000001108",
            "display": "Pneumococcal polysaccharide vaccine solution for injection 0.5ml vials (Alliance Healthcare (Distribution) Ltd)"
         }]},
         "patient": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ce17c772-6b26-11ed-807c-0a58a9feac02"},
         "date": "2022-11-23",
         "primarySource": true,
         "manufacturer": {"reference": "Organization/manufacturer-2089901000001107"},
         "doseQuantity":          {
            "value": "0.5",
            "unit": "ml",
            "system": "http://unitsofmeasure.org",
            "code": "ml"
         },
         "practitioner": [         {
            "role": {"coding":             [
                              {
                  "system": "http://hl7.org/fhir/v2/0443",
                  "code": "EP",
                  "display": "Entering Provider"
               },
                              {
                  "system": "http://hl7.org/fhir/stu3/valueset-immunization-role.html",
                  "code": "AP",
                  "display": "Administering Provider"
               }
            ]},
            "actor": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
         }],
         "note": [{"text": "Added in a consultation to be saved as draft\nAdministered by organisation: Green Lane Medical Centre"}]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "manufacturer-2089901000001107",
         "meta":          {
            "versionId": "2e3dd9f9236fd9fbb0debb6117babe49",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "active": true,
         "name": "Alliance Healthcare (Distribution) Ltd"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "aa03284a-4a42-11ed-b4a4-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "aa03284a-4a42-11ed-b4a4-0a58a9feac02"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-10-12T16:29:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aa03284a-4a42-11ed-b4a4-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/aa07f5f0-4a42-11ed-a4ed-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aa07f5f0-4a42-11ed-a4ed-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "date": "2022-10-12T16:29:29+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Topic 1",
         "entry":          [
            {"item": {"reference": "List/ac58c53c-4a42-11ed-ac21-0a58a9feac02"}},
            {"item": {"reference": "List/d5ed4f54-6b25-11ed-930c-0a0382d71aaa"}},
            {"item": {"reference": "List/59b0aca0-6b26-11ed-9ff1-0a0382d71aaa"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ac58c53c-4a42-11ed-ac21-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry":          [
            {"item": {"reference": "Observation/b24b3d3a-4a42-11ed-a977-0a58a9feac02"}},
            {"item": {"reference": "Observation/d0db2dfa-4a42-11ed-bbd4-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "b24b3d3a-4a42-11ed-a977-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "b24b3d3a-4a42-11ed-a977-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "effectiveDateTime": "2022-10-12",
         "issued": "2022-10-12T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Hi there"
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "d0db2dfa-4a42-11ed-bbd4-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d0db2dfa-4a42-11ed-bbd4-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "71620000",
            "display": "Fracture of femur",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "118977010"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "effectiveDateTime": "2022-10-12",
         "issued": "2022-10-12T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "left leg"
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d5ed4f54-6b25-11ed-930c-0a0382d71aaa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Immunization/e7f4da46-6b25-11ed-9add-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Immunization",
         "id": "e7f4da46-6b25-11ed-9add-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Immunization-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DateRecorded-1",
               "valueDateTime": "2022-11-23T11:56:46+00:00"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-VaccinationProcedure-1",
               "valueCodeableConcept": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "151061000119101",
                  "display": "Tetanus toxoid vaccination given",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "3331232013"
                     }]
                  }]
               }]}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e7f4da46-6b25-11ed-9add-0a58a9feac02"
         }],
         "status": "completed",
         "notGiven": false,
         "vaccineCode": {"coding": [         {
            "system": "http://hl7.org/fhir/v3/NullFlavor",
            "code": "UNK",
            "display": "Unknown"
         }]},
         "patient": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "date": "2022-10-12",
         "primarySource": true,
         "practitioner":          [
                        {
               "role": {"coding": [               {
                  "system": "http://hl7.org/fhir/v2/0443",
                  "code": "EP",
                  "display": "Entering Provider"
               }]},
               "actor": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            },
                        {
               "role": {"coding": [               {
                  "system": "http://hl7.org/fhir/stu3/valueset-immunization-role.html",
                  "code": "AP",
                  "display": "Administering Provider"
               }]},
               "actor": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "note": [{"text": "Administered by organisation: Green Lane Medical Centre"}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "59b0aca0-6b26-11ed-9ff1-0a0382d71aaa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Evaluation",
         "entry": [{"item": {"reference": "Immunization/7d5269fa-6b26-11ed-abc1-0a0382d71aaa"}}]
      }},
      {"resource":       {
         "resourceType": "Immunization",
         "id": "7d5269fa-6b26-11ed-abc1-0a0382d71aaa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Immunization-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DateRecorded-1",
               "valueDateTime": "2022-11-23T12:00:57+00:00"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-VaccinationProcedure-1",
               "valueCodeableConcept": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "1324681000000101",
                  "display": "Administration of first dose of SARS-CoV-2 (severe acute respiratory syndrome coronavirus 2) vaccine"
               }]}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "7d5269fa-6b26-11ed-abc1-0a0382d71aaa"
         }],
         "status": "completed",
         "notGiven": false,
         "vaccineCode": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "39326911000001101",
            "display": "Spikevax COVID-19 mRNA (nucleoside modified) Vaccine 0.1mg/0.5ml dose dispersion for injection multidose vials (Moderna, Inc)"
         }]},
         "patient": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"},
         "date": "2022-10-12",
         "primarySource": true,
         "manufacturer": {"reference": "Organization/manufacturer-39326711000001103"},
         "route": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "78421000",
            "display": "Intramuscular"
         }]},
         "doseQuantity":          {
            "value": "0.1",
            "unit": "ml",
            "system": "http://unitsofmeasure.org",
            "code": "ml"
         },
         "practitioner": [         {
            "role": {"coding":             [
                              {
                  "system": "http://hl7.org/fhir/v2/0443",
                  "code": "EP",
                  "display": "Entering Provider"
               },
                              {
                  "system": "http://hl7.org/fhir/stu3/valueset-immunization-role.html",
                  "code": "AP",
                  "display": "Administering Provider"
               }
            ]},
            "actor": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
         }],
         "note": [{"text": "Administered by organisation: Green Lane Medical Centre"}]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "manufacturer-39326711000001103",
         "meta":          {
            "versionId": "8866b94c5856c3eb42a936e24deae235",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "active": true,
         "name": "Moderna, Inc"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "a74ab406-3e3f-11ed-a4e0-06ac6343f75e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "a74ab406-3e3f-11ed-a4e0-06ac6343f75e"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/bec0705a-dcf9-11ec-9729-0adf11b1c68e"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "Dr Smith"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-09-27T09:34:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "bec0705a-dcf9-11ec-9729-0adf11b1c68e",
         "meta":          {
            "versionId": "bdbd564f40ac7df066fbb30935602be9",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Lee Anderson",
            "family": "Lee Anderson"
         }]
      }},
      {"resource":       {
         "resourceType": "PractitionerRole",
         "id": "87b5a31ab71dc77c8069b2b41e3b9657",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1"]},
         "practitioner": {"reference": "Practitioner/bec0705a-dcf9-11ec-9729-0adf11b1c68e"},
         "organization": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "a74ab406-3e3f-11ed-a4e0-06ac6343f75e-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/a76ac462-3e3f-11ed-8edc-06ac6343f75e"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "a76ac462-3e3f-11ed-8edc-06ac6343f75e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"},
         "date": "2022-09-27T09:37:43+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Joint pain",
         "entry": [{"item": {"reference": "List/aadea62c-3e3f-11ed-919e-06ac6343f75e"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aadea62c-3e3f-11ed-919e-06ac6343f75e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/a4707f94-44b2-11ed-aa59-06799d888942"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "a4707f94-44b2-11ed-aa59-06799d888942",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "a4707f94-44b2-11ed-aa59-06799d888942"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"},
         "effectiveDateTime": "2022-09-27",
         "issued": "2022-09-27T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Test case for Flora"
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "473e837c-eb1e-11ec-93bb-0a06f4112c2e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "major"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "sibling"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/d7d24850-ec9b-11ec-a086-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "child"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/a0e9e322-e64a-11ec-a54f-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "parent"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/69bf3b5c-ec9b-11ec-914a-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "ReferralRequest/fcfaf3d0-fbae-11ec-8f3c-0625e63b315a"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "MedicationRequest/mr-cdcf495e-44b4-11ed-8273-06799d888942"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/3a580f56-eca0-11ec-8c0d-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/645a6996-ec93-11ec-a9cc-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/a4707f94-44b2-11ed-aa59-06799d888942"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "473e837c-eb1e-11ec-93bb-0a06f4112c2e"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "90560007",
            "display": "Gout",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "150085018"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "onsetDateTime": "2000-01-23",
         "assertedDate": "2022-06-13T14:39:41+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "note": [{"text": "Episode: First"}]
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "a0e9e322-e64a-11ec-a54f-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "minor"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "child"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/f515e198-ebcd-11ec-b79c-0a361c06cf60"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "parent"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/de8fd02e-e64a-11ec-98f8-0a58a9feac02"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "a0e9e322-e64a-11ec-a54f-0a58a9feac02"
         }],
         "clinicalStatus": "inactive",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "47933007",
            "display": "Foot pain",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "494960013"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "abatementDateTime": "2022-06-15T00:00:00+01:00",
         "assertedDate": "2022-06-07T11:14:34+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "f515e198-ebcd-11ec-b79c-0a361c06cf60",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "minor"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "child"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/a2033584-ec9d-11ec-9da8-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "parent"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/a0e9e322-e64a-11ec-a54f-0a58a9feac02"}
                  }
               ]
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "AllergyIntolerance/a16d599a-f933-11ec-8781-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "ReferralRequest/6c27b6e8-f921-11ec-96e7-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "AllergyIntolerance/c3595e08-0358-11ed-93c9-0a58a9feac02"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "f515e198-ebcd-11ec-b79c-0a361c06cf60"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "247234006",
            "display": "Ear finding",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "1224006016"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Ear observation"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "onsetDateTime": "2022-06-14",
         "assertedDate": "2022-06-14T11:37:15+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "note": [{"text": "Noting that ear's has a lot of wax, needs removing."}]
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "a2033584-ec9d-11ec-9da8-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "minor"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "parent"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/f515e198-ebcd-11ec-b79c-0a361c06cf60"}
                  }
               ]
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "a2033584-ec9d-11ec-9da8-0a58a9feac02"
         }],
         "clinicalStatus": "inactive",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "1475003",
            "display": "Herpes labialis",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "476681015"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Cold sore"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "onsetDateTime": "2021-03-22",
         "abatementDateTime": "2022-06-15T00:00:00+01:00",
         "assertedDate": "2022-06-15T12:23:51+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "69bf3b5c-ec9b-11ec-914a-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "minor"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "child"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
                  }
               ]
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "69bf3b5c-ec9b-11ec-914a-0a58a9feac02"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "35885006",
            "display": "Hyperuricaemia",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "59880015"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Hyperuricemia"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "assertedDate": "2022-06-15T12:07:57+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "d7d24850-ec9b-11ec-a086-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "minor"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
               "extension":                [
                                    {
                     "url": "type",
                     "valueCode": "sibling"
                  },
                                    {
                     "url": "target",
                     "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
                  }
               ]
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d7d24850-ec9b-11ec-a086-0a58a9feac02"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "162397003",
            "display": "Pain in throat",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "2164213014"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Sore throat"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "assertedDate": "2022-06-15T12:11:02+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "8d852a80-2d0d-11ed-b569-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "8d852a80-2d0d-11ed-b569-060154444956"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "Kate Bush"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-09-05T12:25:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8d852a80-2d0d-11ed-b569-060154444956-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8d852a80-2d0d-11ed-b569-060154444956"},
         "date": "2022-09-05T12:27:16+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/8d91ce34-2d0d-11ed-a172-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8d91ce34-2d0d-11ed-a172-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8d852a80-2d0d-11ed-b569-060154444956"},
         "date": "2022-09-05T12:26:15+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Itch",
         "entry": [{"item": {"reference": "List/9610189a-2d0d-11ed-a899-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "9610189a-2d0d-11ed-a899-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8d852a80-2d0d-11ed-b569-060154444956"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/ace35e74-2d0d-11ed-a8e4-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "ace35e74-2d0d-11ed-a8e4-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ace35e74-2d0d-11ed-a8e4-060154444956"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8d852a80-2d0d-11ed-b569-060154444956"},
         "effectiveDateTime": "2022-09-05",
         "issued": "2022-09-05T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Dry skin itch"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "3915ca34-2d0f-11ed-9be0-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "3915ca34-2d0f-11ed-9be0-060154444956"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/11e98e94f11c929e350b39bb791adf1e"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/0620dd83026c6b2e0f89678587fb24c2"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "Sherman Klump"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-09-01"},
         "serviceProvider": {"reference": "Organization/B86068"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "11e98e94f11c929e350b39bb791adf1e",
         "meta":          {
            "versionId": "d8ccbbd98b1bbb0aeaec7ad544adfed3",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Dr Norbit",
            "family": "Dr Norbit"
         }]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "B86068",
         "meta":          {
            "versionId": "2c77288789d2a913c578750dc0f5e3aa",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "B86068"
         }],
         "active": true,
         "name": "ABBEY GRANGE MEDICAL PRACTICE"
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "0620dd83026c6b2e0f89678587fb24c2",
         "meta":          {
            "versionId": "5fab8f14271769c5e7d4ac68431eabe1",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Ace Ventura",
            "family": "Ace Ventura"
         }]
      }},
      {"resource":       {
         "resourceType": "PractitionerRole",
         "id": "80c32a061982e1e33c0164409b36246f",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1"]},
         "practitioner": {"reference": "Practitioner/0620dd83026c6b2e0f89678587fb24c2"},
         "organization": {"reference": "Organization/B86068"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "3915ca34-2d0f-11ed-9be0-060154444956-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3915ca34-2d0f-11ed-9be0-060154444956"},
         "date": "2022-09-05T12:38:35+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/391b71be-2d0f-11ed-8282-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "391b71be-2d0f-11ed-8282-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3915ca34-2d0f-11ed-9be0-060154444956"},
         "date": "2022-09-05T12:38:12+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Itching",
         "entry": [{"item": {"reference": "List/3f952a08-2d0f-11ed-9dae-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "3f952a08-2d0f-11ed-9dae-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3915ca34-2d0f-11ed-9be0-060154444956"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/438d30c4-2d0f-11ed-a1a0-060154444956"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "438d30c4-2d0f-11ed-a1a0-060154444956",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "438d30c4-2d0f-11ed-a1a0-060154444956"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/3915ca34-2d0f-11ed-9be0-060154444956"},
         "effectiveDateTime": "2022-09-01",
         "issued": "2022-09-01T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Testing Testing"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "a888195e-1e1d-11ed-9d1c-0a62dd4a2fce",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-08-17T12:13:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "a888195e-1e1d-11ed-9d1c-0a62dd4a2fce-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/a88f55d4-1e1d-11ed-860c-0a62dd4a2fce"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "a88f55d4-1e1d-11ed-860c-0a62dd4a2fce",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"},
         "date": "2022-08-17T12:13:44+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Foot callus",
         "entry": [{"item": {"reference": "List/bc35b484-1e1d-11ed-bcc3-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "bc35b484-1e1d-11ed-bcc3-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/d000f776-1e1d-11ed-91f7-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "d000f776-1e1d-11ed-91f7-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d000f776-1e1d-11ed-91f7-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"},
         "effectiveDateTime": "2022-08-17",
         "issued": "2022-08-17T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Very dry"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "251c066c-189f-11ed-ba13-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "251c066c-189f-11ed-ba13-0627edbb51ba"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-08-10T12:25:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "251c066c-189f-11ed-ba13-0627edbb51ba-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/251f6262-189f-11ed-9a80-0627edbb51ba"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "251f6262-189f-11ed-9a80-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"},
         "date": "2022-08-10T12:25:32+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Heart attack",
         "entry": [{"item": {"reference": "List/2cf4e44e-189f-11ed-bfd5-0627edbb51ba"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "2cf4e44e-189f-11ed-bfd5-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry":          [
            {"item": {"reference": "Observation/30d64aee-189f-11ed-b0ea-0627edbb51ba"}},
            {"item": {"reference": "MedicationRequest/mr-5acba862-189f-11ed-909d-0627edbb51ba"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "30d64aee-189f-11ed-b0ea-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "30d64aee-189f-11ed-b0ea-0627edbb51ba"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"},
         "effectiveDateTime": "2022-08-10",
         "issued": "2022-08-10T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Last year"
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-5acba862-189f-11ed-909d-0627edbb51ba",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-5acba862-189f-11ed-909d-0627edbb51ba"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"},
         "status": "active",
         "basedOn": [{"reference": "MedicationRequest/mr-5acba862-189f-11ed-909d-0627edbb51ba"}],
         "medicationReference": {"reference": "Medication/90332006"},
         "effectivePeriod": {"start": "2022-08-10"},
         "dateAsserted": "2022-08-10",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "90332006",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "90332006",
            "display": "Paracetamol",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "108100001000001110"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-5acba862-189f-11ed-909d-0627edbb51ba",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-5acba862-189f-11ed-909d-0627edbb51ba"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "active",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/90332006"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-08-10",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-08-10",
            "end": "2022-08-10"
         }},
         "context": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "d0b02c66-189e-11ed-9d1e-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d0b02c66-189e-11ed-9d1e-0627edbb51ba"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-08-10T12:23:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d0b02c66-189e-11ed-9d1e-0627edbb51ba-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d0b02c66-189e-11ed-9d1e-0627edbb51ba"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/d0b52b62-189e-11ed-a130-0627edbb51ba"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d0b52b62-189e-11ed-a130-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d0b02c66-189e-11ed-9d1e-0627edbb51ba"},
         "date": "2022-08-10T12:23:10+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Breathing problem",
         "entry": [{"item": {"reference": "List/d998ccfc-189e-11ed-9477-0627edbb51ba"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d998ccfc-189e-11ed-9477-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d0b02c66-189e-11ed-9d1e-0627edbb51ba"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/e206036e-189e-11ed-bad6-0627edbb51ba"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "e206036e-189e-11ed-bad6-0627edbb51ba",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e206036e-189e-11ed-bad6-0627edbb51ba"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/d0b02c66-189e-11ed-9d1e-0627edbb51ba"},
         "effectiveDateTime": "2022-08-10",
         "issued": "2022-08-10T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Breathing stopped"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "472a0e4a-126c-11ed-b901-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "472a0e4a-126c-11ed-b901-0680b4bc421a"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-08-02T15:06:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "472a0e4a-126c-11ed-b901-0680b4bc421a-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/472cdb34-126c-11ed-9e12-0680b4bc421a"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "472cdb34-126c-11ed-9e12-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "date": "2022-08-02T15:06:17+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Migraine",
         "entry":          [
            {"item": {"reference": "List/563d6e0e-126c-11ed-b781-0680b4bc421a"}},
            {"item": {"reference": "List/feacafa6-1270-11ed-92b1-0680b4bc421a"}},
            {"item": {"reference": "List/f483d9a8-1272-11ed-999c-067a5ee3abde"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "563d6e0e-126c-11ed-b781-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry":          [
            {"item": {"reference": "Observation/370ebc14-1270-11ed-b697-0680b4bc421a"}},
            {"item": {"reference": "Observation/802cca3e-126c-11ed-be02-0680b4bc421a"}},
            {"item": {"reference": "MedicationRequest/mr-508dc76c-126f-11ed-8440-0680b4bc421a"}},
            {"item": {"reference": "MedicationRequest/mr-53dd48da-126e-11ed-8cc4-0680b4bc421a"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "370ebc14-1270-11ed-b697-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "370ebc14-1270-11ed-b697-0680b4bc421a"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "effectiveDateTime": "2022-08-02",
         "issued": "2022-08-02T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Patient recalls that the migraine is most severe when regular meals become irregular and when alcohol intake has increased during holidays and family events."
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "802cca3e-126c-11ed-be02-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "802cca3e-126c-11ed-be02-0680b4bc421a"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "163051000000102",
            "display": "Family History",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "214961000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "effectiveDateTime": "2022-08-02",
         "issued": "2022-08-02T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Mother has had a history of severe migraine attacks during her early years aged between 25 and 35, becoming less frequent after age of 35 and recently migraines have dissapated."
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-508dc76c-126f-11ed-8440-0680b4bc421a",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-508dc76c-126f-11ed-8440-0680b4bc421a"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept": {"coding": [            {
               "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
               "code": "prescribed-by-another-organisation",
               "display": "Prescribed by another organisation"
            }]}
         }],
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "status": "active",
         "basedOn": [{"reference": "MedicationRequest/mr-508dc76c-126f-11ed-8440-0680b4bc421a"}],
         "medicationReference": {"reference": "Medication/40589005"},
         "effectivePeriod": {"start": "2021-08-02"},
         "dateAsserted": "2021-08-02",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}],
         "note": [{"text": "Additional Information: Prescribed by a foreign doctor whilst on holiday to alleviate the severity of the migraine which helped, but this medication has not been used since. "}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "40589005",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "40589005",
            "display": "Amitriptyline",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "107607101000001116"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-508dc76c-126f-11ed-8440-0680b4bc421a",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-508dc76c-126f-11ed-8440-0680b4bc421a"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"coding": [            {
               "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1",
               "code": "acute",
               "display": "Acute"
            }]}
         }],
         "status": "active",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/40589005"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-08-02",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2021-08-02",
            "end": "2021-08-02"
         }},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"}
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-53dd48da-126e-11ed-8cc4-0680b4bc421a",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-53dd48da-126e-11ed-8cc4-0680b4bc421a"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "status": "active",
         "basedOn": [{"reference": "MedicationRequest/mr-53dd48da-126e-11ed-8cc4-0680b4bc421a"}],
         "medicationReference": {"reference": "Medication/322822007"},
         "effectivePeriod": {"start": "2022-08-02"},
         "dateAsserted": "2022-08-02",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}],
         "note": [{"text": "Additional Information: Used OTC Sumatriptan tablets only during the migraine attacks, got some relief but not affective at other times."}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "322822007",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "322822007",
            "display": "Sumatriptan",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "105031401000001118"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-53dd48da-126e-11ed-8cc4-0680b4bc421a",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-53dd48da-126e-11ed-8cc4-0680b4bc421a"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "active",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/322822007"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-08-02",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-08-02",
            "end": "2022-08-02"
         }},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "feacafa6-1270-11ed-92b1-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Evaluation",
         "entry": [{"item": {"reference": "Observation/29fe2dce-1271-11ed-b691-067a5ee3abde"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "29fe2dce-1271-11ed-b691-067a5ee3abde",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "29fe2dce-1271-11ed-b691-067a5ee3abde"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "effectiveDateTime": "2022-08-02",
         "issued": "2022-08-02T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Patient is reluctant to drugs as a treatment option and has asked if there are other treatment methods. This practice can provide Acupuncture as a form of alternate treatment."
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "f483d9a8-1272-11ed-999c-067a5ee3abde",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry":          [
            {"item": {"reference": "Observation/0ee73f88-1273-11ed-ab43-067a5ee3abde"}},
            {"item": {"reference": "ProcedureRequest/7975b898-1273-11ed-aa6a-067a5ee3abde"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "0ee73f88-1273-11ed-ab43-067a5ee3abde",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "0ee73f88-1273-11ed-ab43-067a5ee3abde"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "44868003",
            "display": "Acupuncture",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "74844017"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "effectiveDateTime": "2022-08-02",
         "issued": "2022-08-02T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Book acupuncture session, when next migraine attack occurs"
      }},
      {"resource":       {
         "resourceType": "ProcedureRequest",
         "id": "7975b898-1273-11ed-aa6a-067a5ee3abde",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProcedureRequest-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "7975b898-1273-11ed-aa6a-067a5ee3abde"
         }],
         "status": "active",
         "intent": "plan",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "44868003",
            "display": "Acupuncture",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "74844017"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"},
         "occurrencePeriod":          {
            "start": "2022-08-02",
            "end": "2023-08-01"
         },
         "authoredOn": "2022-08-02T15:06:00+01:00",
         "requester": {"agent": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "6b0f7678-1268-11ed-94aa-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "6b0f7678-1268-11ed-94aa-0680b4bc421a"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-08-02T14:38:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "6b0f7678-1268-11ed-94aa-0680b4bc421a-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/6b0f7678-1268-11ed-94aa-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/6b140af8-1268-11ed-814f-0680b4bc421a"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "6b140af8-1268-11ed-814f-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/6b0f7678-1268-11ed-94aa-0680b4bc421a"},
         "date": "2022-08-02T14:38:40+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Viral bronchitis",
         "entry": [{"item": {"reference": "List/7edc5734-1268-11ed-80dc-0680b4bc421a"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "7edc5734-1268-11ed-80dc-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/6b0f7678-1268-11ed-94aa-0680b4bc421a"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/9f5928f2-1268-11ed-90f6-0680b4bc421a"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "9f5928f2-1268-11ed-90f6-0680b4bc421a",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "9f5928f2-1268-11ed-90f6-0680b4bc421a"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "49727002",
            "display": "Cough",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "82824016"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/6b0f7678-1268-11ed-94aa-0680b4bc421a"},
         "effectiveDateTime": "2022-08-02",
         "issued": "2022-08-02T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "ef4d2adc-0df1-11ed-af46-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ef4d2adc-0df1-11ed-af46-0a58a9feac02"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325921000000107",
            "display": "Consultation via video conference",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600851000000117"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/bec0705a-dcf9-11ec-9729-0adf11b1c68e"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "John Doe"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-27T22:18:00+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Location",
         "id": "89dfcc66-db44-11ec-8e01-0a58a9feac02",
         "meta":          {
            "versionId": "63d1cfd7bb61f7b6eafaa251861baefe",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Location-1"]
         },
         "status": "active",
         "name": "Test Site for Consultations",
         "address": [{"use": "work"}],
         "telecom": [         {
            "system": "phone",
            "value": "+441134568907",
            "use": "work"
         }],
         "managingOrganization": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ef4d2adc-0df1-11ed-af46-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Consultation via video conference",
         "entry": [{"item": {"reference": "List/ef4fa258-0df1-11ed-9d6e-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ef4fa258-0df1-11ed-9d6e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"},
         "date": "2022-07-27T22:20:27+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Hypertension",
         "entry": [{"item": {"reference": "List/1382aa26-0df2-11ed-b978-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "1382aa26-0df2-11ed-b978-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/3ef6da7e-0df2-11ed-8354-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "3ef6da7e-0df2-11ed-8354-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "3ef6da7e-0df2-11ed-8354-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"},
         "effectiveDateTime": "2022-07-27",
         "issued": "2022-07-27T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "The patient belives they have angina, but no medical records exist to state otherwise"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "e6d7bb86-0db2-11ed-9400-0ae7b3177ca0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325891000000104",
            "display": "Consultation by telephone",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600791000000117"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/bec0705a-dcf9-11ec-9729-0adf11b1c68e"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/8b9d1140-9bbf-11ec-991d-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "John Doe"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-27T14:47:00+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "e6d7bb86-0db2-11ed-9400-0ae7b3177ca0-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Consultation by telephone",
         "entry": [{"item": {"reference": "List/e6dd62d4-0db2-11ed-9f67-0ae7b3177ca0"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "e6dd62d4-0db2-11ed-9f67-0ae7b3177ca0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"},
         "date": "2022-07-27T14:49:14+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Osteopetrosis",
         "entry": [{"item": {"reference": "List/23a1cfb6-0db3-11ed-9451-0ae7b3177ca0"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "23a1cfb6-0db3-11ed-9451-0ae7b3177ca0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Observation/58a58ebe-0db3-11ed-b8cf-0ae7b3177ca0"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "58a58ebe-0db3-11ed-b8cf-0ae7b3177ca0",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "58a58ebe-0db3-11ed-b8cf-0ae7b3177ca0"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "385342005",
            "display": "Bone density finding",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "599311000000113"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Bone density"
                  }
               ]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"},
         "effectiveDateTime": "2022-07-27",
         "issued": "2022-07-27T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Arrange an referral visit to the hospital for a DEXA scan"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "7aef3822-0cb8-11ed-921a-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "7aef3822-0cb8-11ed-921a-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-26T08:56:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "7aef3822-0cb8-11ed-921a-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/7af3245a-0cb8-11ed-a997-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "7af3245a-0cb8-11ed-a997-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"},
         "date": "2022-07-26T08:56:39+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Breathing problem",
         "entry": [{"item": {"reference": "List/8f4caeb2-0cb8-11ed-835c-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8f4caeb2-0cb8-11ed-835c-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry":          [
            {"item": {"reference": "Observation/9b65baf4-0cb8-11ed-a32e-0a58a9feac02"}},
            {"item": {"reference": "MedicationRequest/mr-ec36a1b4-0cb8-11ed-a685-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "9b65baf4-0cb8-11ed-a32e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "9b65baf4-0cb8-11ed-a32e-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "249369003",
            "display": "Sinus catarrh",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "372078013"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"},
         "effectiveDateTime": "2022-07-01",
         "issued": "2022-07-01T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-ec36a1b4-0cb8-11ed-a685-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-ec36a1b4-0cb8-11ed-a685-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"},
         "status": "completed",
         "basedOn": [{"reference": "MedicationRequest/mr-ec36a1b4-0cb8-11ed-a685-0a58a9feac02"}],
         "medicationReference": {"reference": "Medication/16037711000001105"},
         "effectivePeriod":          {
            "start": "2022-07-05",
            "end": "2022-07-05"
         },
         "dateAsserted": "2022-07-01",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "16037711000001105",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "16037711000001105",
            "display": "Fentanyl 200micrograms/dose nasal spray",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "56671501000001114"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-ec36a1b4-0cb8-11ed-a685-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-ec36a1b4-0cb8-11ed-a685-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "completed",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/16037711000001105"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-07-26",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-07-05",
            "end": "2022-07-05"
         }},
         "context": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "9666b784-0bfe-11ed-8fc6-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "9666b784-0bfe-11ed-8fc6-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-25T10:45:00+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "9666b784-0bfe-11ed-8fc6-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/9666b784-0bfe-11ed-8fc6-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/966af9b6-0bfe-11ed-ad62-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "966af9b6-0bfe-11ed-ad62-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/9666b784-0bfe-11ed-8fc6-0a58a9feac02"},
         "date": "2022-07-25T10:45:59+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Dry eyes",
         "entry": [{"item": {"reference": "List/a4f14774-0bfe-11ed-b254-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "a4f14774-0bfe-11ed-b254-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/9666b784-0bfe-11ed-8fc6-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/b34991c8-0bfe-11ed-837e-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "b34991c8-0bfe-11ed-837e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "b34991c8-0bfe-11ed-837e-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "275892006",
            "display": "Conjunctival swab taken",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "411860015"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/9666b784-0bfe-11ed-8fc6-0a58a9feac02"},
         "effectiveDateTime": "2022-07-25",
         "issued": "2022-07-25T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Some notes"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "62344a46-0cc4-11ed-8691-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "62344a46-0cc4-11ed-8691-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/6f255871a295f43797693f4ae75b4722"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-23T10:21:00+01:00"},
         "serviceProvider": {"reference": "Organization/B86068"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "6f255871a295f43797693f4ae75b4722",
         "meta":          {
            "versionId": "ce7a112298bdeb8f49e3fb1a40d324c0",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Dr Do Little",
            "family": "Dr Do Little"
         }]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "62344a46-0cc4-11ed-8691-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/6235e4b4-0cc4-11ed-81c8-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "6235e4b4-0cc4-11ed-81c8-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"},
         "date": "2022-07-26T10:21:51+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Falling injury",
         "entry": [{"item": {"reference": "List/7135e950-0cc4-11ed-9575-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "7135e950-0cc4-11ed-9575-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry":          [
            {"item": {"reference": "Observation/773eae5e-0cc4-11ed-bc46-0a58a9feac02"}},
            {"item": {"reference": "MedicationRequest/mr-9082f2c6-0cc4-11ed-81cb-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "773eae5e-0cc4-11ed-bc46-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "773eae5e-0cc4-11ed-bc46-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "248491001",
            "display": "Swollen knee",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "370925016"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"},
         "effectiveDateTime": "2022-07-23",
         "issued": "2022-07-23T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-9082f2c6-0cc4-11ed-81cb-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-9082f2c6-0cc4-11ed-81cb-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"},
         "status": "completed",
         "basedOn": [{"reference": "MedicationRequest/mr-9082f2c6-0cc4-11ed-81cb-0a58a9feac02"}],
         "medicationReference": {"reference": "Medication/9523311000001106"},
         "effectivePeriod":          {
            "start": "2022-07-25",
            "end": "2022-07-25"
         },
         "dateAsserted": "2022-07-23",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "9523311000001106",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "9523311000001106",
            "display": "Deep Heat rub (The Mentholatum Company Ltd)",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "73110301000001112"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-9082f2c6-0cc4-11ed-81cb-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-9082f2c6-0cc4-11ed-81cb-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "completed",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/9523311000001106"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-07-26",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-07-25",
            "end": "2022-07-25"
         }},
         "context": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "cb696516-3346-11ed-bbcf-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "cb696516-3346-11ed-bbcf-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/6f255871a295f43797693f4ae75b4722"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "Sally Fearon"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-15T19:00:00+01:00"},
         "serviceProvider": {"reference": "Organization/B83034"}
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "B83034",
         "meta":          {
            "versionId": "4bc8951552b62a003a9e704232cce713",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "B83034"
         }],
         "active": true,
         "name": "GRANGE MEDICAL CENTRE"
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "cb696516-3346-11ed-bbcf-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"},
         "date": "2022-09-14T02:04:35+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/cb753a6c-3346-11ed-a4db-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "cb753a6c-3346-11ed-a4db-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/713cb804-3346-11ed-a223-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"},
         "date": "2022-09-13T10:31:07+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Breathing problem",
         "entry": [{"item": {"reference": "List/eb07531a-3346-11ed-add4-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "eb07531a-3346-11ed-add4-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry":          [
            {"item": {"reference": "Observation/04b21e3a-3347-11ed-a911-0a58a9feac02"}},
            {"item": {"reference": "MedicationRequest/mr-c491a2ca-3347-11ed-b7dd-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "04b21e3a-3347-11ed-a911-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "04b21e3a-3347-11ed-a911-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "230145002",
            "display": "Difficulty breathing",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "344917018"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"},
         "effectiveDateTime": "2022-07-15",
         "issued": "2022-07-15T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Swollen nose, nasal passage inflamed."
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-c491a2ca-3347-11ed-b7dd-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-c491a2ca-3347-11ed-b7dd-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"},
         "status": "completed",
         "basedOn": [{"reference": "MedicationRequest/mr-c491a2ca-3347-11ed-b7dd-0a58a9feac02"}],
         "medicationReference": {"reference": "Medication/39111911000001107"},
         "effectivePeriod":          {
            "start": "2022-07-18",
            "end": "2022-07-18"
         },
         "dateAsserted": "2022-07-15",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}],
         "note": [{"text": "Additional Information: If symptoms continue after 2 days, consult your GP"}]
      }},
      {"resource":       {
         "resourceType": "Medication",
         "id": "39111911000001107",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "39111911000001107",
            "display": "Beclometasone 50micrograms/dose nasal spray",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "1674561000001118"
               }]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-c491a2ca-3347-11ed-b7dd-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-c491a2ca-3347-11ed-b7dd-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "completed",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/39111911000001107"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-09-13",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-07-18",
            "end": "2022-07-18"
         }},
         "context": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Condition",
         "id": "713cb804-3346-11ed-a223-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ProblemHeader-Condition-1"]},
         "extension":          [
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1",
               "valueCode": "major"
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "Observation/04b21e3a-3347-11ed-a911-0a58a9feac02"}
            },
                        {
               "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1",
               "valueReference": {"reference": "MedicationRequest/mr-c491a2ca-3347-11ed-b7dd-0a58a9feac02"}
            }
         ],
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "713cb804-3346-11ed-a223-0a58a9feac02"
         }],
         "clinicalStatus": "active",
         "category": [{"coding": [         {
            "system": "http://hl7.org/fhir/condition-category",
            "code": "problem-list-item",
            "display": "Problem List Item"
         }]}],
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "36971009",
            "display": "Sinusitis",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "61668014"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "onsetDateTime": "2022-03-05",
         "assertedDate": "2022-09-13T10:28:35+01:00",
         "asserter": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "note":          [
            {"text": "Hard to breathe through your nose for at least a week"},
            {"text": "Episode: First"}
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "76cfa608-0cba-11ed-8ed2-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "76cfa608-0cba-11ed-8ed2-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/6f255871a295f43797693f4ae75b4722"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-15T09:10:00+01:00"},
         "serviceProvider": {"reference": "Organization/5N204"}
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "5N204",
         "meta":          {
            "versionId": "893dc5d7c12642d6178483c7fb394563",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "5N204"
         }],
         "active": true,
         "name": "FARTOWN GRANGE MEDICAL CENTRE"
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "76cfa608-0cba-11ed-8ed2-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/76d11b8c-0cba-11ed-bdd9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "76d11b8c-0cba-11ed-bdd9-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"},
         "date": "2022-07-26T09:10:51+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Falling injury",
         "entry": [{"item": {"reference": "List/890faa02-0cba-11ed-84b7-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "890faa02-0cba-11ed-84b7-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry":          [
            {"item": {"reference": "Observation/93d21e5c-0cba-11ed-bc5c-0a58a9feac02"}},
            {"item": {"reference": "MedicationRequest/mr-e3f94612-0cba-11ed-9509-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "93d21e5c-0cba-11ed-bc5c-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "93d21e5c-0cba-11ed-bc5c-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "267039000",
            "display": "Swollen ankle",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "397898016"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"},
         "effectiveDateTime": "2022-07-15",
         "issued": "2022-07-15T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Dont fall"
      }},
      {"resource":       {
         "resourceType": "MedicationStatement",
         "id": "ms-e3f94612-0cba-11ed-9509-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ms-e3f94612-0cba-11ed-9509-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescribingAgency-1",
            "valueCodeableConcept":             {
               "coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescribingAgency-1",
                  "code": "prescribed-by-another-organisation",
                  "display": "Prescribed by another organisation"
               }],
               "text": "Over the counter medication"
            }
         }],
         "context": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"},
         "status": "completed",
         "basedOn": [{"reference": "MedicationRequest/mr-e3f94612-0cba-11ed-9509-0a58a9feac02"}],
         "medicationReference": {"reference": "Medication/9523311000001106"},
         "effectivePeriod":          {
            "start": "2022-07-18",
            "end": "2022-07-18"
         },
         "dateAsserted": "2022-07-15",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "taken": "unk",
         "dosage": [{"text": "Not recorded"}]
      }},
      {"resource":       {
         "resourceType": "MedicationRequest",
         "id": "mr-e3f94612-0cba-11ed-9509-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "mr-e3f94612-0cba-11ed-9509-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"]},
         "extension": [         {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {"text": "No information available"}
         }],
         "status": "completed",
         "intent": "plan",
         "medicationReference": {"reference": "Medication/9523311000001106"},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "authoredOn": "2022-07-26",
         "recorder": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
         "dosageInstruction": [{"text": "Not recorded"}],
         "dispenseRequest": {"validityPeriod":          {
            "start": "2022-07-18",
            "end": "2022-07-18"
         }},
         "context": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "ab663cd0-0358-11ed-b5cf-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ab663cd0-0358-11ed-b5cf-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-14T10:38:02+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ab663cd0-0358-11ed-b5cf-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/ab6a9618-0358-11ed-9501-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ab6a9618-0358-11ed-9501-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f515e198-ebcd-11ec-b79c-0a361c06cf60"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"},
         "date": "2022-07-14T10:38:08+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Head pain",
         "entry": [{"item": {"reference": "List/b7067924-0358-11ed-851c-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "b7067924-0358-11ed-851c-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "AllergyIntolerance/c3595e08-0358-11ed-93c9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "AllergyIntolerance",
         "id": "c3595e08-0358-11ed-93c9-0a58a9feac02",
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "c3595e08-0358-11ed-93c9-0a58a9feac02"
         }],
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1"]},
         "extension": [         {
            "url": "http://hl7.org/fhir/StructureDefinition/encounter-associatedEncounter",
            "valueReference": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"}
         }],
         "verificationStatus": "unconfirmed",
         "assertedDate": "2022-07-14T00:00:00+01:00",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "767468001",
            "display": "Allergy to pea",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "3671670018"
               }]
            }]
         }]},
         "clinicalStatus": "active",
         "patient": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "recorder": {"reference": "Practitioner/7fffae6a-9bbf-11ec-9064-0ae647c12c72"},
         "category": ["medication"],
         "reaction": [         {
            "manifestation": [{"coding": [            {
               "system": "http://hl7.org/fhir/v3/NullFlavor",
               "code": "NI",
               "display": "NoInformation"
            }]}],
            "severity": "mild"
         }]
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "7fffae6a-9bbf-11ec-9064-0ae647c12c72",
         "meta":          {
            "versionId": "5b8c31e8fbaaf0c1ab47ef42e1a36e45",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": " Caroline Endley",
            "family": " Caroline Endley"
         }]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "3a23e042-fc67-11ec-960e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "3a23e042-fc67-11ec-960e-0a58a9feac02"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-05T14:34:33+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "3a23e042-fc67-11ec-960e-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/3a2624a6-fc67-11ec-9c8f-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "3a2624a6-fc67-11ec-9c8f-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"},
         "date": "2022-07-05T14:34:42+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Foot joint finding",
         "entry": [{"item": {"reference": "List/bbbab112-fc67-11ec-a1b0-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "bbbab112-fc67-11ec-a1b0-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/c6cdec4a-fc67-11ec-9dc9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "c6cdec4a-fc67-11ec-9dc9-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "c6cdec4a-fc67-11ec-9dc9-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "75367002",
            "display": "Blood pressure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "125176019"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"},
         "effectiveDateTime": "2022-07-05",
         "issued": "2022-07-05T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
            {"reference": "Organization/N82090"}
         ],
         "interpretation": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "3442003",
            "display": "Better",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "6816018"
               }]
            }]
         }]},
         "comment": "test",
         "bodySite": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "368208006",
            "display": "Left upper arm structure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "507686016"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Left arm"
                  }
               ]
            }]
         }]},
         "component":          [
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271649006",
                  "display": "Systolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406507015"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 130,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            },
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271650006",
                  "display": "Diastolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406508013"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 81,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            }
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "10b0993c-fbb6-11ec-b62a-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "10b0993c-fbb6-11ec-b62a-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325891000000104",
            "display": "Consultation by telephone",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600791000000117"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-04T17:26:25+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "10b0993c-fbb6-11ec-b62a-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Consultation by telephone",
         "entry": [{"item": {"reference": "List/10b53d0c-fbb6-11ec-a358-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "10b53d0c-fbb6-11ec-a358-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"},
         "date": "2022-07-04T17:26:32+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Anginal syndrome",
         "entry": [{"item": {"reference": "List/17b1206c-fbb6-11ec-a626-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "17b1206c-fbb6-11ec-a626-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "DocumentReference/emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "DocumentReference",
         "id": "emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-DocumentReference-1"]},
         "masterIdentifier":          {
            "system": "https://medicus.health",
            "value": "emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"
         },
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"
         }],
         "status": "current",
         "type":          {
            "coding": [            {
               "system": "http://snomed.info/sct",
               "code": "751481000000104",
               "display": "eMED3 (2010) new statement issued, not fit for work",
               "extension": [               {
                  "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [                  {
                     "url": "descriptionId",
                     "valueId": "1653351000000114"
                  }]
               }]
            }],
            "text": "eMED3 (2010) new statement issued, not fit for work"
         },
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "created": "2022-07-04",
         "indexed": "2022-07-04T17:27:10+01:00",
         "author": [{"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}],
         "custodian": {"reference": "Organization/N82090"},
         "description": "Fit note (04 Jul 2022, Diagnosis: Anginal syndrome)",
         "content": [{"attachment":          {
            "contentType": "application/pdf",
            "size": 315497,
            "url": "https://a30005.api.training.england.medicus.health/N82090/STU3/1/gpconnect/documents/Binary/emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"
         }}],
         "context": {"encounter": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"}}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "149f8db8-fb80-11ec-b080-0656c2ef588e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "149f8db8-fb80-11ec-b080-0656c2ef588e"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-07-04T11:00:02+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "149f8db8-fb80-11ec-b080-0656c2ef588e-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/14a13802-fb80-11ec-84f5-0656c2ef588e"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "14a13802-fb80-11ec-84f5-0656c2ef588e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"},
         "date": "2022-07-04T11:00:06+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Heart murmur absent",
         "entry": [{"item": {"reference": "List/16d806e6-fb80-11ec-b269-0656c2ef588e"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "16d806e6-fb80-11ec-b269-0656c2ef588e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry": [{"item": {"reference": "Observation/4972df40-fb80-11ec-96b1-0656c2ef588e"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "4972df40-fb80-11ec-96b1-0656c2ef588e",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "4972df40-fb80-11ec-96b1-0656c2ef588e"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"},
         "effectiveDateTime": "2022-07-04",
         "issued": "2022-07-04T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "test note"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "4f27b680-f90b-11ec-9e82-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "4f27b680-f90b-11ec-9e82-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325891000000104",
            "display": "Consultation by telephone",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600791000000117"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/3fc69aced516f38466d6554ba75ae5c7"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/663d3250-d77d-11ec-8a40-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period":          {
            "start": "2022-07-01T07:58:36+01:00",
            "end": "2022-07-01T08:02:00+01:00"
         },
         "length":          {
            "value": 3,
            "unit": "m",
            "system": "http://unitsofmeasure.org",
            "code": "min"
         },
         "serviceProvider": {"reference": "Organization/FRY06"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "3fc69aced516f38466d6554ba75ae5c7",
         "meta":          {
            "versionId": "190ec05af2c51bcd231a2220e172fb63",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Resp Prac 1",
            "family": "Resp Prac 1"
         }]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "FRY06",
         "meta":          {
            "versionId": "c5e60c8193919c7b88678b0a608d87c9",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "identifier": [         {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FRY06"
         }],
         "active": true,
         "name": "BROWN AND FRANCIS"
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "663d3250-d77d-11ec-8a40-0a58a9feac02",
         "meta":          {
            "versionId": "b0d6adc124d48ff787568bcd2851eb7a",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Gina Jacobs",
            "family": "Gina Jacobs"
         }]
      }},
      {"resource":       {
         "resourceType": "PractitionerRole",
         "id": "f0b7e657c212f63353bbcbbe1e96021b",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1"]},
         "practitioner": {"reference": "Practitioner/663d3250-d77d-11ec-8a40-0a58a9feac02"},
         "organization": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "4f27b680-f90b-11ec-9e82-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Consultation by telephone",
         "entry": [{"item": {"reference": "List/4f2c4592-f90b-11ec-a3c5-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "4f2c4592-f90b-11ec-a3c5-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"},
         "date": "2022-07-01T07:59:10+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Anginal syndrome",
         "entry":          [
            {"item": {"reference": "List/60d587cc-f90b-11ec-ab74-0a58a9feac02"}},
            {"item": {"reference": "List/925e0206-f90b-11ec-932f-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "60d587cc-f90b-11ec-ab74-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "DocumentReference/emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "DocumentReference",
         "id": "emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-DocumentReference-1"]},
         "masterIdentifier":          {
            "system": "https://medicus.health",
            "value": "emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"
         },
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"
         }],
         "status": "current",
         "type":          {
            "coding": [            {
               "system": "http://snomed.info/sct",
               "code": "751481000000104",
               "display": "eMED3 (2010) new statement issued, not fit for work",
               "extension": [               {
                  "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                  "extension": [                  {
                     "url": "descriptionId",
                     "valueId": "1653351000000114"
                  }]
               }]
            }],
            "text": "eMED3 (2010) new statement issued, not fit for work"
         },
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "created": "2022-07-01",
         "indexed": "2022-07-01T08:00:49+01:00",
         "author": [{"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}],
         "custodian": {"reference": "Organization/N82090"},
         "description": "Fit note (01 Jul 2022, Diagnosis: Anginal syndrome)",
         "content": [{"attachment":          {
            "contentType": "application/pdf",
            "size": 315497,
            "url": "https://a30005.api.training.england.medicus.health/N82090/STU3/1/gpconnect/documents/Binary/emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"
         }}],
         "context": {"encounter": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"}}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "925e0206-f90b-11ec-932f-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/971117de-f90b-11ec-9c7d-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "971117de-f90b-11ec-9c7d-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "971117de-f90b-11ec-9c7d-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "194828000",
            "display": "Angina pectoris",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "299757012"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"},
         "effectiveDateTime": "2022-07-01",
         "issued": "2022-07-01T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "ee24d42c-f6e3-11ec-abfa-0ad2cc072944",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "ee24d42c-f6e3-11ec-abfa-0ad2cc072944"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-06-28T14:12:05+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ee24d42c-f6e3-11ec-abfa-0ad2cc072944-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/ee28eabc-f6e3-11ec-b3d2-0ad2cc072944"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "ee28eabc-f6e3-11ec-b3d2-0ad2cc072944",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"},
         "date": "2022-06-28T14:12:15+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Topic 1",
         "entry": [{"item": {"reference": "List/fa92e87a-f6e3-11ec-b9cb-0ad2cc072944"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "fa92e87a-f6e3-11ec-b9cb-0ad2cc072944",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "ReferralRequest/13477f2a-f6e4-11ec-8765-0ad2cc072944"}}]
      }},
      {"resource":       {
         "resourceType": "ReferralRequest",
         "id": "13477f2a-f6e4-11ec-8765-0ad2cc072944",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-ReferralRequest-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "13477f2a-f6e4-11ec-8765-0ad2cc072944"
         }],
         "status": "unknown",
         "intent": "order",
         "priority": "routine",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"},
         "authoredOn": "2022-06-28",
         "requester":          {
            "agent": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
            "onBehalfOf": {"reference": "Organization/N82090"}
         },
         "specialty": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "394579002",
            "display": "Cardiology",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "1488309017"
               }]
            }]
         }]},
         "recipient":          [
            {"reference": "Practitioner/13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-practitioner"},
            {"reference": "Organization/13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-organisation"},
            {"reference": "HealthcareService/13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-healthcare-service"}
         ],
         "reasonCode": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "853561000000109",
            "display": "Referral to Angina Plan self-management programme",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "2210191000000118"
               }]
            }]
         }]}],
         "supportingInfo": [{"reference": "DocumentReference/manual-referral-attachment--1350f366-f6e4-11ec-aed2-0ad2cc072944"}]
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-practitioner",
         "meta":          {
            "versionId": "0f4023d0ea076d6fd0ff14b65ad9eaa7",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [{"use": "official"}]
      }},
      {"resource":       {
         "resourceType": "Organization",
         "id": "13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-organisation",
         "meta":          {
            "versionId": "83bc305309cfff0363df827507371141",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"]
         },
         "active": true,
         "name": "Fountain Medical Centre"
      }},
      {"resource":       {
         "resourceType": "HealthcareService",
         "id": "13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-healthcare-service",
         "meta": {"profile": ["https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-HealthcareService-1"]},
         "name": "Cardiology",
         "providedBy": {"reference": "Organization/13477f2a-f6e4-11ec-8765-0ad2cc072944-provider-organisation"}
      }},
      {"resource":       {
         "resourceType": "DocumentReference",
         "id": "manual-referral-attachment--1350f366-f6e4-11ec-aed2-0ad2cc072944",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-DocumentReference-1"]},
         "masterIdentifier":          {
            "system": "https://medicus.health",
            "value": "manual-referral-attachment--1350f366-f6e4-11ec-aed2-0ad2cc072944"
         },
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "manual-referral-attachment--1350f366-f6e4-11ec-aed2-0ad2cc072944"
         }],
         "status": "current",
         "type": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25611000000107",
            "display": "Referral letter",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "63301000000111"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "created": "2022-06-28",
         "indexed": "2022-06-28T14:13:17+01:00",
         "author": [{"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}],
         "custodian": {"reference": "Organization/N82090"},
         "description": "Referral letter",
         "content": [{"attachment":          {
            "contentType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
            "size": 12034,
            "url": "https://a30005.api.training.england.medicus.health/N82090/STU3/1/gpconnect/documents/Binary/manual-referral-attachment--1350f366-f6e4-11ec-aed2-0ad2cc072944"
         }}]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "d9368c8a-ed57-11ec-a21b-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d9368c8a-ed57-11ec-a21b-0a58a9feac02"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period":          {
            "start": "2022-06-16T10:36:37+01:00",
            "end": "2022-06-16T10:55:00+01:00"
         },
         "length":          {
            "value": 18,
            "unit": "m",
            "system": "http://unitsofmeasure.org",
            "code": "min"
         },
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d9368c8a-ed57-11ec-a21b-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d9368c8a-ed57-11ec-a21b-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/d93b698a-ed57-11ec-bca9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "d93b698a-ed57-11ec-bca9-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d9368c8a-ed57-11ec-a21b-0a58a9feac02"},
         "date": "2022-06-16T10:36:50+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "BP - High blood pressure",
         "entry": [{"item": {"reference": "List/e83e8b92-ed57-11ec-a31a-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "e83e8b92-ed57-11ec-a31a-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/d9368c8a-ed57-11ec-a21b-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Observation/045195ea-ed58-11ec-bd26-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "045195ea-ed58-11ec-bd26-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "045195ea-ed58-11ec-bd26-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "967006",
            "display": "Medication education",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "2704019"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/d9368c8a-ed57-11ec-a21b-0a58a9feac02"},
         "effectiveDateTime": "2022-06-16",
         "issued": "2022-06-16T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "aa9b8db4-ec92-11ec-a152-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "aa9b8db4-ec92-11ec-a152-0a58a9feac02"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period":          {
            "start": "2022-06-15T11:03:08+01:00",
            "end": "2022-06-15T11:03:08+01:00"
         },
         "length":          {
            "value": 0,
            "unit": "m",
            "system": "http://unitsofmeasure.org",
            "code": "min"
         },
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aa9b8db4-ec92-11ec-a152-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/aaa0367a-ec92-11ec-8991-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aaa0367a-ec92-11ec-8991-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"},
         "date": "2022-06-15T11:05:21+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Gout",
         "entry": [{"item": {"reference": "List/fbc74444-ec92-11ec-97d5-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "fbc74444-ec92-11ec-97d5-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/645a6996-ec93-11ec-a9cc-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "645a6996-ec93-11ec-a9cc-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "645a6996-ec93-11ec-a9cc-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "75367002",
            "display": "Blood pressure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "125176019"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"},
         "effectiveDateTime": "2022-06-15",
         "issued": "2022-06-15T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "interpretation": {"coding": [         {
            "system": "http://terminology.hl7.org/CodeSystem/v2-0078",
            "code": "H",
            "display": "High"
         }]},
         "bodySite": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "368208006",
            "display": "Left upper arm structure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "507686016"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Left arm"
                  }
               ]
            }]
         }]},
         "component":          [
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271649006",
                  "display": "Systolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406507015"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 142,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            },
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271650006",
                  "display": "Diastolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406508013"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 78,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            }
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "004d5e0a-e675-11ec-984c-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "004d5e0a-e675-11ec-984c-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-06-07T16:17:39+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "004d5e0a-e675-11ec-984c-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/004fc500-e675-11ec-aa56-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "004fc500-e675-11ec-aa56-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"},
         "date": "2022-06-07T16:17:53+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Foot pain",
         "entry": [{"item": {"reference": "List/2fcb541c-eca0-11ec-bfb9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "2fcb541c-eca0-11ec-bfb9-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Observation/3a580f56-eca0-11ec-8c0d-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "3a580f56-eca0-11ec-8c0d-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "3a580f56-eca0-11ec-8c0d-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "413672003",
            "display": "Blood test requested",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "2534090019"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"},
         "effectiveDateTime": "2022-06-07",
         "issued": "2022-06-07T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "931f0b5a-e64a-11ec-967d-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "931f0b5a-e64a-11ec-967d-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-06-07T11:13:36+01:00"},
         "location": [{"location": {"reference": "Location/89dfcc66-db44-11ec-8e01-0a58a9feac02"}}],
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "931f0b5a-e64a-11ec-967d-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/9322f972-e64a-11ec-8c9e-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "9322f972-e64a-11ec-8c9e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/a0e9e322-e64a-11ec-a54f-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"},
         "date": "2022-06-07T11:14:11+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Foot pain",
         "entry": [{"item": {"reference": "List/aa623cce-e64a-11ec-9bed-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "aa623cce-e64a-11ec-9bed-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Plan",
         "entry": [{"item": {"reference": "Observation/de8fd02e-e64a-11ec-98f8-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "de8fd02e-e64a-11ec-98f8-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "de8fd02e-e64a-11ec-98f8-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "249815005",
            "display": "Foot length",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "372676011"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"},
         "effectiveDateTime": "2022-06-07",
         "issued": "2022-06-07T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/bb1e3008-ba45-11ec-9b67-0a58a9feac02"},
            {"reference": "Organization/N82090"}
         ],
         "valueDateTime": "2022-06-01",
         "interpretation": {"coding": [         {
            "system": "http://terminology.hl7.org/CodeSystem/v2-0078",
            "code": "LU",
            "display": "Very low"
         }]},
         "bodySite": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "56459004",
            "display": "Foot structure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension":                [
                                    {
                     "url": "descriptionId",
                     "valueId": "93890013"
                  },
                                    {
                     "url": "descriptionDisplay",
                     "valueString": "Foot"
                  }
               ]
            }]
         }]}
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "8123f97e-d754-11ec-9e89-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "8123f97e-d754-11ec-9e89-0a58a9feac02"
         }],
         "status": "finished",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/90d8388a-9721-11ec-91e1-063fa650175a"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-05-19T10:17:11+01:00"},
         "serviceProvider": {"reference": "Organization/N82090"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "90d8388a-9721-11ec-91e1-063fa650175a",
         "meta":          {
            "versionId": "54e09fe32f7c2c1be1412b98fec9017f",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Pete Salisbury",
            "family": "Pete Salisbury"
         }]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8123f97e-d754-11ec-9e89-0a58a9feac02-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/81285276-d754-11ec-b37e-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "81285276-d754-11ec-b37e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "date": "2022-05-19T10:17:28+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Topic 1",
         "entry":          [
            {"item": {"reference": "List/8bc347b8-d754-11ec-82fd-0a58a9feac02"}},
            {"item": {"reference": "List/c397a6de-d754-11ec-bcbf-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "8bc347b8-d754-11ec-82fd-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "History",
         "entry":          [
            {"item": {"reference": "Observation/9e94ba16-d754-11ec-907e-0a58a9feac02"}},
            {"item": {"reference": "Observation/b766c8e0-d754-11ec-8b67-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "9e94ba16-d754-11ec-907e-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "9e94ba16-d754-11ec-907e-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "37331000000100",
            "display": "Comment note",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "87901000000115"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "issued": "2022-05-19T10:18:17+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Some text notes for a test consultation"
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "b766c8e0-d754-11ec-8b67-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "b766c8e0-d754-11ec-8b67-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "302258001",
            "display": "Back problem",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "443851011"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "issued": "2022-05-19T10:18:59+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ],
         "comment": "Some text about back problem"
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "c397a6de-d754-11ec-bcbf-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry":          [
            {"item": {"reference": "Observation/eeaef1dc-d755-11ec-8d85-0a58a9feac02"}},
            {"item": {"reference": "Observation/d6680cf4-d754-11ec-a7ef-0a58a9feac02"}},
            {"item": {"reference": "Observation/e120ecd2-d755-11ec-91b9-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "eeaef1dc-d755-11ec-8d85-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "eeaef1dc-d755-11ec-8d85-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "289115009",
            "display": "Does not cough",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "428917016"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "issued": "2022-05-19T10:27:41+01:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "d6680cf4-d754-11ec-a7ef-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "d6680cf4-d754-11ec-a7ef-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "75367002",
            "display": "Blood pressure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "125176019"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "effectiveDateTime": "2022-05-19",
         "issued": "2022-05-19T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/90d8388a-9721-11ec-91e1-063fa650175a"},
            {"reference": "Organization/N82090"}
         ],
         "component":          [
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271649006",
                  "display": "Systolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406507015"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 120,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            },
                        {
               "code": {"coding": [               {
                  "system": "http://snomed.info/sct",
                  "code": "271650006",
                  "display": "Diastolic blood pressure",
                  "extension": [                  {
                     "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
                     "extension": [                     {
                        "url": "descriptionId",
                        "valueId": "406508013"
                     }]
                  }]
               }]},
               "valueQuantity":                {
                  "value": 90,
                  "unit": "mm[Hg]",
                  "system": "http://unitsofmeasure.org"
               }
            }
         ]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "e120ecd2-d755-11ec-91b9-0a58a9feac02",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "e120ecd2-d755-11ec-91b9-0a58a9feac02"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "50373000",
            "display": "Body height measure",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "495662010"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"},
         "effectiveDateTime": "2022-05-19",
         "issued": "2022-05-19T00:00:00+01:00",
         "performer":          [
            {"reference": "Practitioner/90d8388a-9721-11ec-91e1-063fa650175a"},
            {"reference": "Organization/N82090"}
         ],
         "valueQuantity":          {
            "value": "175",
            "unit": "cm",
            "system": "http://unitsofmeasure.org",
            "code": "cm"
         },
         "comment": "Some height notes"
      }},
      {"resource":       {
         "resourceType": "Encounter",
         "id": "b54392c6-0816-11ed-9344-069ffbeb8efa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Encounter-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "b54392c6-0816-11ed-9344-069ffbeb8efa"
         }],
         "status": "unknown",
         "type": [{"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325861000000105",
            "display": "Face to face consultation",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "600731000000118"
               }]
            }]
         }]}],
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "participant":          [
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PPRF",
                  "display": "Primary Performer"
               }]}],
               "individual": {"reference": "Practitioner/8f20e0ba344ec4139f3aec1c39721386"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"reference": "Practitioner/6e93577da7e43af47945bb67a61b1a86"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                  "code": "PART",
                  "display": "Participant"
               }]}],
               "individual": {"display": "Winston Baggs"}
            },
                        {
               "type": [{"coding": [               {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-ParticipantType-1",
                  "code": "REC",
                  "display": "Recorder"
               }]}],
               "individual": {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"}
            }
         ],
         "period": {"start": "2022-02-20T00:00:00+00:00"},
         "serviceProvider": {"reference": "Organization/B83034"}
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "8f20e0ba344ec4139f3aec1c39721386",
         "meta":          {
            "versionId": "fb9e283d592cdcb6959cd9dea8238ef6",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Dr Dolittle",
            "family": "Dr Dolittle"
         }]
      }},
      {"resource":       {
         "resourceType": "Practitioner",
         "id": "6e93577da7e43af47945bb67a61b1a86",
         "meta":          {
            "versionId": "80a2b7f8ca6be0703f04ecbcdf78e353",
            "profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"]
         },
         "active": true,
         "name": [         {
            "use": "official",
            "text": "Nurse Gladys Emmanuel",
            "family": "Nurse Gladys Emmanuel"
         }]
      }},
      {"resource":       {
         "resourceType": "PractitionerRole",
         "id": "734c6f49068f3a267e587f5c03701ab5",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1"]},
         "practitioner": {"reference": "Practitioner/6e93577da7e43af47945bb67a61b1a86"},
         "organization": {"reference": "Organization/B83034"}
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "b54392c6-0816-11ed-9344-069ffbeb8efa-consultation",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "325851000000107",
            "display": "Consultation"
         }]},
         "title": "Face to face consultation",
         "entry": [{"item": {"reference": "List/b5476c20-0816-11ed-b4d0-069ffbeb8efa"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "b5476c20-0816-11ed-b4d0-069ffbeb8efa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "extension": [         {
            "url": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1",
            "extension": [            {
               "url": "target",
               "valueReference": {"reference": "Condition/e5225ff6-ec9e-11ec-b38a-0a58a9feac02"}
            }]
         }],
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "25851000000105",
            "display": "Topic (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"},
         "date": "2022-07-20T11:28:34+01:00",
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Heart disease",
         "entry": [{"item": {"reference": "List/33cf4c70-0817-11ed-92c5-069ffbeb8efa"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "id": "33cf4c70-0817-11ed-92c5-069ffbeb8efa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "24781000000107",
            "display": "Category (EHR)"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "encounter": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"},
         "orderedBy": {"coding": [         {
            "system": "http://hl7.org/fhir/list-order",
            "code": "system",
            "display": "Sorted by System"
         }]},
         "title": "Examination",
         "entry": [{"item": {"reference": "Observation/b69c2cfe-0817-11ed-90d9-069ffbeb8efa"}}]
      }},
      {"resource":       {
         "resourceType": "Observation",
         "id": "b69c2cfe-0817-11ed-90d9-069ffbeb8efa",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Observation-1"]},
         "identifier": [         {
            "system": "https://medicus.health",
            "value": "b69c2cfe-0817-11ed-90d9-069ffbeb8efa"
         }],
         "status": "final",
         "code": {"coding": [         {
            "system": "http://snomed.info/sct",
            "code": "390884006",
            "display": "Heart failure follow-up",
            "extension": [            {
               "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid",
               "extension": [               {
                  "url": "descriptionId",
                  "valueId": "1484917012"
               }]
            }]
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "context": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"},
         "effectiveDateTime": "2022-02-20",
         "issued": "2022-02-20T00:00:00+00:00",
         "performer":          [
            {"reference": "Practitioner/748dc0bc-9bbf-11ec-b043-0ae647c12c72"},
            {"reference": "Organization/N82090"}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "List of consultations",
         "code": {"coding": [         {
            "display": "List of consultations",
            "system": "http://snomed.info/sct",
            "code": "1149501000000101"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "Encounter/8dbadb3a-a634-11ed-af2e-0adb7c23cfe0"}},
            {"item": {"reference": "Encounter/fe30e7b0-811d-11ed-825c-064380d115ae"}},
            {"item": {"reference": "Encounter/ce17c772-6b26-11ed-807c-0a58a9feac02"}},
            {"item": {"reference": "Encounter/aa03284a-4a42-11ed-b4a4-0a58a9feac02"}},
            {"item": {"reference": "Encounter/a74ab406-3e3f-11ed-a4e0-06ac6343f75e"}},
            {"item": {"reference": "Encounter/8d852a80-2d0d-11ed-b569-060154444956"}},
            {"item": {"reference": "Encounter/3915ca34-2d0f-11ed-9be0-060154444956"}},
            {"item": {"reference": "Encounter/a888195e-1e1d-11ed-9d1c-0a62dd4a2fce"}},
            {"item": {"reference": "Encounter/251c066c-189f-11ed-ba13-0627edbb51ba"}},
            {"item": {"reference": "Encounter/d0b02c66-189e-11ed-9d1e-0627edbb51ba"}},
            {"item": {"reference": "Encounter/472a0e4a-126c-11ed-b901-0680b4bc421a"}},
            {"item": {"reference": "Encounter/6b0f7678-1268-11ed-94aa-0680b4bc421a"}},
            {"item": {"reference": "Encounter/ef4d2adc-0df1-11ed-af46-0a58a9feac02"}},
            {"item": {"reference": "Encounter/e6d7bb86-0db2-11ed-9400-0ae7b3177ca0"}},
            {"item": {"reference": "Encounter/7aef3822-0cb8-11ed-921a-0a58a9feac02"}},
            {"item": {"reference": "Encounter/9666b784-0bfe-11ed-8fc6-0a58a9feac02"}},
            {"item": {"reference": "Encounter/62344a46-0cc4-11ed-8691-0a58a9feac02"}},
            {"item": {"reference": "Encounter/cb696516-3346-11ed-bbcf-0a58a9feac02"}},
            {"item": {"reference": "Encounter/76cfa608-0cba-11ed-8ed2-0a58a9feac02"}},
            {"item": {"reference": "Encounter/ab663cd0-0358-11ed-b5cf-0a58a9feac02"}},
            {"item": {"reference": "Encounter/3a23e042-fc67-11ec-960e-0a58a9feac02"}},
            {"item": {"reference": "Encounter/10b0993c-fbb6-11ec-b62a-0a58a9feac02"}},
            {"item": {"reference": "Encounter/149f8db8-fb80-11ec-b080-0656c2ef588e"}},
            {"item": {"reference": "Encounter/4f27b680-f90b-11ec-9e82-0a58a9feac02"}},
            {"item": {"reference": "Encounter/ee24d42c-f6e3-11ec-abfa-0ad2cc072944"}},
            {"item": {"reference": "Encounter/d9368c8a-ed57-11ec-a21b-0a58a9feac02"}},
            {"item": {"reference": "Encounter/aa9b8db4-ec92-11ec-a152-0a58a9feac02"}},
            {"item": {"reference": "Encounter/004d5e0a-e675-11ec-984c-0a58a9feac02"}},
            {"item": {"reference": "Encounter/931f0b5a-e64a-11ec-967d-0a58a9feac02"}},
            {"item": {"reference": "Encounter/8123f97e-d754-11ec-9e89-0a58a9feac02"}},
            {"item": {"reference": "Encounter/b54392c6-0816-11ed-9344-069ffbeb8efa"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Problems - linked problems not relating to the primary query",
         "code": {"coding": [         {
            "display": "Problems - linked problems not relating to the primary query",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "problems-linked-problems-not-relating-to-the-primary-query"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}},
            {"item": {"reference": "Condition/e5225ff6-ec9e-11ec-b38a-0a58a9feac02"}},
            {"item": {"reference": "Condition/a0e9e322-e64a-11ec-a54f-0a58a9feac02"}},
            {"item": {"reference": "Condition/f515e198-ebcd-11ec-b79c-0a361c06cf60"}},
            {"item": {"reference": "Condition/a2033584-ec9d-11ec-9da8-0a58a9feac02"}},
            {"item": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}},
            {"item": {"reference": "Condition/69bf3b5c-ec9b-11ec-914a-0a58a9feac02"}},
            {"item": {"reference": "Condition/d7d24850-ec9b-11ec-a086-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - allergies contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - allergies contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-allergies-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry": [{"item": {"reference": "AllergyIntolerance/c3595e08-0358-11ed-93c9-0a58a9feac02"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - diary entries contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - diary entries contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-diary-entries-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry": [{"item": {"reference": "ProcedureRequest/7975b898-1273-11ed-aa6a-067a5ee3abde"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - documents contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - documents contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-documents-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "DocumentReference/emed3-fit-note--274af69c-fbb6-11ec-90aa-0a58a9feac02"}},
            {"item": {"reference": "DocumentReference/emed3-fit-note--89f7e5b4-f90b-11ec-a31f-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - immunisations contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - immunisations contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-immunisations-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "Immunization/0052a54a-6b27-11ed-b999-0a58a9feac02"}},
            {"item": {"reference": "Immunization/e7f4da46-6b25-11ed-9add-0a58a9feac02"}},
            {"item": {"reference": "Immunization/7d5269fa-6b26-11ed-abc1-0a0382d71aaa"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - medications contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - medications contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-medications-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "MedicationStatement/ms-5acba862-189f-11ed-909d-0627edbb51ba"}},
            {"item": {"reference": "MedicationStatement/ms-508dc76c-126f-11ed-8440-0680b4bc421a"}},
            {"item": {"reference": "MedicationStatement/ms-53dd48da-126e-11ed-8cc4-0680b4bc421a"}},
            {"item": {"reference": "MedicationStatement/ms-ec36a1b4-0cb8-11ed-a685-0a58a9feac02"}},
            {"item": {"reference": "MedicationStatement/ms-9082f2c6-0cc4-11ed-81cb-0a58a9feac02"}},
            {"item": {"reference": "MedicationStatement/ms-c491a2ca-3347-11ed-b7dd-0a58a9feac02"}},
            {"item": {"reference": "MedicationStatement/ms-e3f94612-0cba-11ed-9509-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - outbound referrals in consultations",
         "code": {"coding": [         {
            "display": "Consultations - outbound referrals in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-outbound-referrals-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry": [{"item": {"reference": "ReferralRequest/13477f2a-f6e4-11ec-8765-0ad2cc072944"}}]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - problems contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - problems contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-problems-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "Condition/e5225ff6-ec9e-11ec-b38a-0a58a9feac02"}},
            {"item": {"reference": "Condition/473e837c-eb1e-11ec-93bb-0a06f4112c2e"}},
            {"item": {"reference": "Condition/f057a9a8-ec9e-11ec-ab85-0a58a9feac02"}},
            {"item": {"reference": "Condition/713cb804-3346-11ed-a223-0a58a9feac02"}},
            {"item": {"reference": "Condition/f515e198-ebcd-11ec-b79c-0a361c06cf60"}},
            {"item": {"reference": "Condition/a0e9e322-e64a-11ec-a54f-0a58a9feac02"}}
         ]
      }},
      {"resource":       {
         "resourceType": "List",
         "meta": {"profile": ["https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1"]},
         "status": "current",
         "mode": "snapshot",
         "title": "Consultations - uncategorised data contained in consultations",
         "code": {"coding": [         {
            "display": "Consultations - uncategorised data contained in consultations",
            "system": "https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1",
            "code": "consultations-uncategorised-data-contained-in-consultations"
         }]},
         "subject": {"reference": "Patient/4d59c916-9726-11ec-af3f-0a58a9feac02"},
         "entry":          [
            {"item": {"reference": "Observation/df0d1240-a635-11ed-a297-0a58a9feac02"}},
            {"item": {"reference": "Observation/e9e8a03a-a635-11ed-85f8-0adb7c23cfe0"}},
            {"item": {"reference": "Observation/f3b4148c-a635-11ed-a3d3-0a58a9feac02"}},
            {"item": {"reference": "Observation/114bcc3e-811e-11ed-8063-0a58a9feac02"}},
            {"item": {"reference": "Observation/b24b3d3a-4a42-11ed-a977-0a58a9feac02"}},
            {"item": {"reference": "Observation/d0db2dfa-4a42-11ed-bbd4-0a58a9feac02"}},
            {"item": {"reference": "Observation/a4707f94-44b2-11ed-aa59-06799d888942"}},
            {"item": {"reference": "Observation/ace35e74-2d0d-11ed-a8e4-060154444956"}},
            {"item": {"reference": "Observation/438d30c4-2d0f-11ed-a1a0-060154444956"}},
            {"item": {"reference": "Observation/d000f776-1e1d-11ed-91f7-0a58a9feac02"}},
            {"item": {"reference": "Observation/30d64aee-189f-11ed-b0ea-0627edbb51ba"}},
            {"item": {"reference": "Observation/e206036e-189e-11ed-bad6-0627edbb51ba"}},
            {"item": {"reference": "Observation/370ebc14-1270-11ed-b697-0680b4bc421a"}},
            {"item": {"reference": "Observation/802cca3e-126c-11ed-be02-0680b4bc421a"}},
            {"item": {"reference": "Observation/29fe2dce-1271-11ed-b691-067a5ee3abde"}},
            {"item": {"reference": "Observation/0ee73f88-1273-11ed-ab43-067a5ee3abde"}},
            {"item": {"reference": "Observation/9f5928f2-1268-11ed-90f6-0680b4bc421a"}},
            {"item": {"reference": "Observation/3ef6da7e-0df2-11ed-8354-0a58a9feac02"}},
            {"item": {"reference": "Observation/58a58ebe-0db3-11ed-b8cf-0ae7b3177ca0"}},
            {"item": {"reference": "Observation/9b65baf4-0cb8-11ed-a32e-0a58a9feac02"}},
            {"item": {"reference": "Observation/b34991c8-0bfe-11ed-837e-0a58a9feac02"}},
            {"item": {"reference": "Observation/773eae5e-0cc4-11ed-bc46-0a58a9feac02"}},
            {"item": {"reference": "Observation/04b21e3a-3347-11ed-a911-0a58a9feac02"}},
            {"item": {"reference": "Observation/93d21e5c-0cba-11ed-bc5c-0a58a9feac02"}},
            {"item": {"reference": "Observation/c6cdec4a-fc67-11ec-9dc9-0a58a9feac02"}},
            {"item": {"reference": "Observation/4972df40-fb80-11ec-96b1-0656c2ef588e"}},
            {"item": {"reference": "Observation/971117de-f90b-11ec-9c7d-0a58a9feac02"}},
            {"item": {"reference": "Observation/045195ea-ed58-11ec-bd26-0a58a9feac02"}},
            {"item": {"reference": "Observation/645a6996-ec93-11ec-a9cc-0a58a9feac02"}},
            {"item": {"reference": "Observation/3a580f56-eca0-11ec-8c0d-0a58a9feac02"}},
            {"item": {"reference": "Observation/de8fd02e-e64a-11ec-98f8-0a58a9feac02"}},
            {"item": {"reference": "Observation/9e94ba16-d754-11ec-907e-0a58a9feac02"}},
            {"item": {"reference": "Observation/b766c8e0-d754-11ec-8b67-0a58a9feac02"}},
            {"item": {"reference": "Observation/eeaef1dc-d755-11ec-8d85-0a58a9feac02"}},
            {"item": {"reference": "Observation/d6680cf4-d754-11ec-a7ef-0a58a9feac02"}},
            {"item": {"reference": "Observation/e120ecd2-d755-11ec-91b9-0a58a9feac02"}},
            {"item": {"reference": "Observation/b69c2cfe-0817-11ed-90d9-069ffbeb8efa"}}
         ]
      }}
   ]
}
```