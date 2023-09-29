## {{page-title}}

## Prerequisites ##

### Consumer ###

The consumer system:

- **SHALL** have previously resolved the organisation's FHIR endpoint base URL

## API usage ##

### Request operation ###

#### FHIR relative request ####

```http
GET /metadata
```

#### FHIR absolute request ####

```http
GET https://[proxy_server]/https://[provider_server]/[fhir_base]/metadata
```

#### Payload request body ####

N/A

### Request response ###

#### Response Headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- **SHALL** return a `200` **OK** HTTP status code on successful retrieval of the capability statement
- **SHALL** return a capability statement which conforms to the standard [FHIR CapabilityStatement](http://hl7.org/fhir/STU3/capabilitystatement.html)

An example GP Connect CapabilityStatement is shown below ready for customisation and embedding into GP Connect assured provider systems. Providers should use this CapabilityStatement as a base for their own CapabilityStatement, replacing the element in square brackets (`[` & `]`) with specific information of their implementation. The main version at the top of the CapabilityStatement should represent the GP Connect specification version which the FHIR server implements.

Consumer systems:
- **SHOULD** request the capability statement from the FHIR server endpoint in order to ascertain details of the implementation of GP Connect capabilities delivered by the FHIR server
- consumers may also cache the capability statement information retrieved from an endpoint to reduce the number of future calls they make to the target organization's FHIR server


#### Error handling ####

Provider systems are expected to always be able to return a valid capability statement.


### Examples ###

#### Get the capability statement ####

##### Request

```
GET https://[proxy_server]/https://[provider_server]/[fhir_base]/metadata
```

Consumers SHALL include the following additional HTTP request headers:

| Header	| Value |
| ------ | ----- |
| Ssp-TraceID | Consumer’s TraceID (i.e. GUID/UUID) |
| Ssp-From | Consumer’s ASID |
| Ssp-To | Provider’s ASID |
| Ssp-InteractionID | urn:nhs:names:services:gpconnect:fhir:rest:read:metadata-1 |



##### Response

```json
{
  "resourceType": "CapabilityStatement",
  "version": "1.2.7",
  "name": "GP Connect",
  "status": "active",
  "date": "2020-01-15",
  "publisher": "[Provider Software Vendor Name]",
  "contact": [
    {
      "name": "[Provider Software Vendor Contact Name]"
    }
  ],
  "description": "This server implements the GP Connect API version 1.2.7",
  "copyright": "Copyright NHS Digital 2016-20",
  "kind": "capability",
  "software": {
    "name": "[Provider Software Name]",
    "version": "[Provider Software Version]",
    "releaseDate": "[Provider Software Release Date]"
  },
  "fhirVersion": "3.0.1",
  "acceptUnknown": "both",
  "format": [
    "application/fhir+json",
    "application/fhir+xml"
  ],
  "profile": [
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Patient-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-PractitionerRole-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Location-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Schedule-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Slot-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-AllergyIntolerance-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationStatement-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-List-1" },
      { "reference": "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1" }
  ],
  "rest": [
    {
      "mode": "server",
      "security": {
        "cors": true
      },
      "resource": [
        {
          "type": "Patient",
          "interaction": [
            {
              "code": "read"
            },
            {
              "code": "search-type"
            }
          ],
          "searchParam": [
            {
              "name": "identifier",
              "type": "token",
              "documentation": "NHS Number (i.e. https://fhir.nhs.uk/Id/nhs-number|123456789)"
            }
          ]
        },
        {
          "type": "Organization",
          "interaction": [
            {
              "code": "read"
            },
            {
              "code": "search-type"
            }
          ],
          "searchParam": [
            {
              "name": "identifier",
              "type": "token",
              "documentation": "ODS Code (i.e. https://fhir.nhs.uk/Id/ods-organization-code|Y12345)"
            }
          ]
        },
        {
          "type": "Practitioner",
          "interaction": [
            {
              "code": "read"
            },
            {
              "code": "search-type"
            }
          ],
          "searchParam": [
            {
              "name": "identifier",
              "type": "token",
              "documentation": "SDS User Id (i.e. https://fhir.nhs.uk/Id/sds-user-id|999999)"
            }
          ]
        },
        {
          "type": "Location",
          "interaction": [
            {
              "code": "read"
            }
          ]
        },
        {
          "type": "Appointment",
          "interaction": [
            {
              "code": "read"
            },
            {
              "code": "create"
            },
            {
              "code": "update"
            },
            {
              "code": "search-type"
            }
          ],
          "updateCreate": false,
          "searchParam": [
            {
              "name": "identifier",
              "type": "token",
              "documentation": "NHS Number (i.e. https://fhir.nhs.uk/Id/nhs-number|123456789)"
            }
          ]
        },
        {
          "type": "Slot",
          "interaction": [
            {
              "code": "search-type"
            }
          ],
          "searchInclude": [
            "Schedule:actor:Location",
            "Schedule:actor:Practitioner",
            "Slot:schedule",
            "Location:managingOrganization"
          ],
          "searchParam": [
            {
              "name": "start",
              "type": "date"
            },
            {
              "name": "end",
              "type": "date"
            },
            {
              "name": "status",
              "type": "token"
            },
            {
              "name": "searchFilter",
              "type": "token"
            }
          ]
        }
      ],
      "operation": [
        {
          "name": "gpc.registerpatient",
          "definition": {
            "reference": "https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-RegisterPatient-Operation-1"
          }
        },
        {
          "name": "gpc.getstructuredrecord",
          "definition": {
            "reference": "https://fhir.nhs.uk/STU3/OperationDefinition/GPConnect-GetStructuredRecord-Operation-1/_history/1.12"
          }
        }
      ]
    }
  ]
}
```