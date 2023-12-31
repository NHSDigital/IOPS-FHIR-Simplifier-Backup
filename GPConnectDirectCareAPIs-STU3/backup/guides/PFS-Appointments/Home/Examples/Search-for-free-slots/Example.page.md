## {{page-title}}

## FHIR relative request

```fhir
GET /Slot?[start={search_prefix}start_date]
          [&end=[{search_prefix}end_date]
          [&status=free]
          [&_include=Slot:schedule]
          {&_include:recurse=Schedule:actor:Practitioner}
          {&_include:recurse=Schedule:actor:Location}
          {&_include:recurse=Location:managingOrganization}
          {&searchFilter={OrgTypeCodeSystem}|{OrgTypeCode}}
          {&searchFilter={OrgODSCodeSystem}|{OrgODSCode}}

```

## FHIR absolute request

```fhir
GET https://[proxy_server]/https://[provider_server]/[fhir_base]
          /Slot?[start={search_prefix}start_date]
          [&end=[{search_prefix}end_date]
          [&status=free]
          [&_include=Slot:schedule]
          {&_include:recurse=Schedule:actor:Practitioner}
          {&_include:recurse=Schedule:actor:Location}
          {&_include:recurse=Location:managingOrganization}
          {&searchFilter={OrgTypeCodeSystem}|{OrgTypeCode}}
          {&searchFilter={OrgODSCodeSystem}|{OrgODSCode}}

```

## Example response

```json

{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": [
    {
      "resource": {
        "resourceType": "Slot",
        "id": "1584",
        "meta": {
          "versionId": "1471219260000",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Slot-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-DeliveryChannel-2",
            "valueCode": "In-person"
          }
        ],
        "serviceType": [
          {
            "text": "General GP Appointment"
          }
        ],
        "schedule": {
          "reference": "Schedule/14"
        },
        "status": "free",
        "start": "2016-08-15T11:30:00+01:00",
        "end": "2016-08-15T11:40:00+01:00"
      }
    },
    {
      "resource": {
        "resourceType": "Slot",
        "id": "1644",
        "meta": {
          "versionId": "1471219260112",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Slot-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-DeliveryChannel-2",
            "valueCode": "In-person"
          }
        ],
        "serviceType": [
          {
            "text": "NHS Health Check"
          }
        ],
        "schedule": {
          "reference": "Schedule/14"
        },
        "status": "free",
        "start": "2016-08-15T11:40:00+01:00",
        "end": "2016-08-15T11:50:00+01:00"
      }
    },
    {
      "resource": {
        "resourceType": "Schedule",
        "id": "14",
        "meta": {
          "versionId": "1469444400000",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Schedule-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-GPConnect-PractitionerRole-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-SDSJobRoleName-1",
                  "code": "R0260",
                  "display": "General Medical Practitioner"
                }
              ]
            }
          }
        ],
        "serviceCategory": {
          "text": "General GP Appointments"
        },
        "actor": [
          {
            "reference": "Location/17"
          },
          {
            "reference": "Practitioner/2"
          }
        ],
        "planningHorizon": {
          "start": "2016-08-15T09:00:00+01:00",
          "end": "2016-08-15T12:00:00+01:00"
        }
      }
    },
    {
      "resource": {
        "resourceType": "Practitioner",
        "id": "2",
        "meta": {
          "versionId": "636064088099800115",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1"
          ]
        },
        "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "111122223333"
          }
        ],
        "name": [
          {
            "family": "Black",
            "given": [
              "Sarah"
            ],
            "prefix": [
              "Mrs"
            ]
          }
        ],
        "gender": "female"
      }
    },
    {
      "resource": {
        "resourceType": "Location",
        "id": "17",
        "meta": {
          "versionId": "636064088100870233",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Location-1"
          ]
        },
        "name": "The Trevelyan Practice",
        "address": {
          "line": [
            "Trevelyan Square",
            "Boar Ln",
            "Leeds"
          ],
          "postalCode": "LS1 6AE"
        },
        "telecom": {
          "system": "phone",
          "value": "03003035678",
          "use": "work"
        },
        "managingOrganization": {
          "reference": "Organization/23"
        }
      }
    },
    {
      "resource": {
        "resourceType": "Organization",
        "id": "23",
        "meta": {
          "versionId": "636064088098730113",
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1"
          ]
        },
        "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "A00001"
          }
        ],
        "name": "The Trevelyan Practice",
        "address": {
          "line": [
            "Trevelyan Square",
            "Boar Ln"
          ],
          "city": "Leeds",
          "district": "West Yorkshire",
          "postalCode": "LS1 6AE"
        },
        "telecom": {
          "system": "phone",
          "value": "03003035678",
          "use": "work"
        }
      }
    }
  ]
}

```



---