---
topic: how-to-search-for-free-slots
---

## {{page-title}}

## Use case ##

This specification describes a single use case enabling the consumer to request from the targeted provider system slots matching the selected date range, booking organisation ODS Code and Type, and other parameters including UC Disposition Code and Service ID. 

Refer to {{pagelink:Home/Design/Interactions/Appointment-consumer-sessions.page.md}} for how this API use case could be used in the context of a typical consumer appointment management session.

## Security ##

GP Connect utilises a JSON Web Tokens (JWT) to transmit clinical audit and provenance detail.

## Search parameters ##

Provider systems **SHALL** support the following search parameters:

| Name | Type | Description | Paths |
|---|---|---|---|
| `status` | `token` | The free/busy status of the appointment | `Slot.status` |
| `start` | `date` or `dateTime` | Slot start date, or date and time | `Slot.start` |
| `end` | `date` or `dateTime` | Slot end date, or date and time | `Slot.end` |
| `searchFilter` | `token` | A generic token to allow consumers to pass additional search criteria to the provider. | (n/a) |

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> The supported search parameters should be included in the <a href="./FHIR-Capability-Statement.page.md"> FHIR Capability Statement</a>.
</div>

## _include parameters ##

Provider systems **SHALL** support the following include parameters:

| Name | Description | Paths |
|---|---|---|
| `_include=Slot:schedule` | Include `Schedule` resources referenced within the returned `Slot` resources | `Slot.schedule` |
| `_include:recurse= Schedule:actor:Practitioner` | Include `Practitioner` resources referenced within the returned `Schedule` resources | `Schedule.actor:Practitioner` |
| `_include:recurse= Schedule:actor:Location` | Include `Location` resources referenced within the returned `Schedule` resources | `Schedule.actor:Location` |
| `_include:recurse= Location:managingOrganization` | Include `Organization` resources references from matching `Location` resources | `Location.managingOrganization` |

Consumer systems **SHALL** send the following parameters in the request:

- the `start` parameter **SHALL** only be included once in the request
- the `start` parameter **SHALL** be supplied with the `ge` search prefix - for example, `start=ge2017-09-22`, which indicates that the consumer would like slots where the slot start date is on or after "2017-09-22"
- the `end` parameter **SHALL** only be included once in the request
- the `end` parameter **SHALL** be supplied with the `le` search prefix - for example, `end=le2017-09-26`, which indicates that the consumer would like slots where the slot end date is on or before "2017-09-26"

{{render:Searchforfreeslotstimeline.png}}

- the `start` and `end` parameters **SHALL** contain a search prefix as specified above, and:
  - either, a `date` in the format `yyyy-mm-dd`. Partial dates are not allowed.
  - or, a `dateTime` in the format `yyyy-mm-ddThh:mm:ss+hh:mm` in (UK) local time, with the timezone offset `+00:00` for UTC and `+01:00` for BST

- `status=free` specifies that only free slots will be returned (the slot status value of `free` **SHALL** be specified, other slot status values are not permitted)

- `_include=Slot:schedule` specifies that associated `Schedule` resources are returned

Consumer systems **SHOULD** send the following parameters in the request:

- `searchFilter` parameters - see [Enhanced slot filtering](#enhanced-slot-filtering)

Consumer systems **MAY** send the following *_include* parameters in the request, to minimise the number of API calls required to prepare an appointment booking:

- `_include:recurse=Schedule:actor:Practitioner`
- `_include:recurse=Schedule:actor:Location`
- `_include:recurse=Location:managingOrganization`

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> Search for free slots does not prevent searching for slots in the past, but all other appointment management capabilities do not allow for appointment management where the appointments start date element is in the past. Therefore, slots found in the past cannot be used to book an appointment.
</div>

### Enhanced slot filtering ###

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> It is recognized that provider systems must offer GP practices more functionality to enable them to better manage their available appointment slots in the light of increasing access requirements from other organisations. GP Connect has specified additional provider requirements to enable this. These additional requirements are outlined in {{pagelink:Home/Design/Interactions/Slot-availability-management.page.md}}
</div>

In order for providers to return the appropriate slots for the consumer, the consumer **SHOULD** send in the following parameters using the `searchFilter` parameter using the [token](https://www.hl7.org/fhir/STU3/search.html#token) parameter format of `system|code`:

| Parameter name | Parameter value - system element | Parameter value - code element |
| --- | --- |
| `searchFilter` | `https://fhir.nhs.uk/Id/ods-organization-code` | Consumer ODS organisation code, e.g. `A11111`|
| `searchFilter` | `https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1` | Consumer organisation type code from [GPConnect-OrganisationType-1 valueset](https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1), e.g. `urgent-care` |

Where search filters are sent by consumers which are not explicitly supported in this specification (for example, urgent care uses a disposition code value set), providers who do not understand the additional parameters **SHALL** ignore them and **SHALL NOT** return an error.

## Booking multiple adjacent slots ##

See the conditions in which a consumer may book multiple adjacent slots: [Book an appointment](https://simplifier.net/guide/pfs-appointments/home-design-slot-availability-management?version=current#booking-multiple-adjacent-slots).

## Consumer display requirements ##

The fields below allow a patient to choose and attend an appointment appropriate to their needs.

In order to prevent incorrect or unsuitable bookings, and to allow a patient to attend the appointment at the correct time, place or via the correct delivery channel, consumer systems **SHALL** support the following fields: 

- start date and time
- delivery channel (in-person, telephone, video)
- slot type and schedule type (see `Slot.serviceType` and `Schedule.serviceCategory`)
- location name (for example, Fairfax Clinic)
- practitioner role (for example, General Medical Practitioner, Nurse)
- practitioner name and gender

## Prerequisites ##

### Consumer ###

The consumer system:

- **SHALL** have previously resolved the organisation's FHIR&reg; endpoint base URL through the endpoint lookup process
- **SHALL** request a maximum date range covering a two-week period

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> Multiple separate API calls can be made if a larger date range is required. However, consideration should be given to the load this places on the provider system.
</div>

## API usage ##

### Request operation ###

#### FHIR relative request ####

```http
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

#### FHIR absolute request ####

```http
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

#### Payload request body ####

N/A

### Request response ###

#### FHIR resource relationships ####

This diagram shows the relationships between FHIR resources in the search for free slots response message.

Diagram - Slot resource relationship structure

{{render:appointment-fhir-resources-slot.png}}

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> Schedule may not have Practitioner references present in the actor element, and therefore the Practitioner resource may not be returned in the response Bundle, regardless of the _include parameters sent.
</div>

#### Response headers ####

Provider systems are not expected to add any specific headers beyond that described in the HTTP and FHIR&reg; standards.

#### Payload response body ####

Provider systems:

- **SHALL** return a `200` **OK** HTTP status code on successful retrieval of free slot details

- **SHALL** return resources conforming to the GP Connect profiled versions of the base FHIR resources listed on the {{pagelink:Home/Build/FHIR-Resources.page.md}} page

- **SHALL** return a `Bundle` of type `searchset` containing:

  - `Slot` resources for the organisation which:
    - have a `status` of `free`
    - **and** fall fully within the requested date range - that is, free slots which start before the `start` parameter and free slots which end after `end` search parameter **SHALL NOT** be returned
    - **and** are bookable according to related defined [embargo/booking window](https://simplifier.net/guide/pfs-appointments/home-design-slot-availability-management?version=current#booking-windowembargo) rules 
    - **and** which match the search filter parameters of Booking Organisation (ODS Code) and/or organisation type, or are not restricted for booking by ODS code and/or organisation type

  - `Schedule` resources associated with the returned `Slot` resources

  - `Practitioner` resources associated to the returned `Schedule` resources, where available, and where requested by the consumer using the `_include:recurse=Schedule:actor:Practitioner` parameter

    - **SHALL** populate the `Practitioner` resource according to population requirements for [Read a practitioner](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_read_a_practitioner.html#payload-response-body)

  - `Location` resources associated with the returned `Schedule` resources, where requested by the consumer using the `_include:recurse=Schedule:actor:Location` parameter

    - the `Location` referenced from the `Schedule` resource **SHALL** represent the location of the surgery where the appointment will take place.  `Location.managingOrganization` **SHALL** be populated - see {{pagelink:Home/Design/Design-principles/Branch-Surgeries.page.md}} for more details.

    - **SHALL** populate the `Location` resource according to population requirements for [Read a location](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_read_a_location.html#payload-response-body)

  - an `Organization` resource associated with the `Location` resources (via `Location.managingOrganization`) associated with the `Schedule`

    - this resource **SHALL** always be present, regardless of parameters, except where no slots are returned. See {{pagelink:known-issues}} for more details

    - provider systems **SHALL** accept the `_include:recurse=Location:managingOrganization` parameter in the Search for free slots request without returning an error, however **SHALL** continue to return the `Organization` resource regardless of whether this is present

    - **SHALL** populate the `Organization` resource according to population requirements for [Read an organization](https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_read_an_organisation.html#payload-response-body)

- if no free slots are returned for the requested time period then an empty response `Bundle` **SHALL** be returned

- only `Schedule`, `Practitioner`, `Location` and `Organization` resources **SHALL** be returned where they are associated with the `Slot` resources matching the query

- **SHALL** populate `Slot.start`, `Slot.end`, `Schedule.planningHorizon.start` and `**SHALL**.planningHorizon.end` elements in (UK) local time in the format `yyyy-mm-ddThh:mm:ss+hh:mm`, with the timezone offset `+00:00` for UTC and `+01:00` for BST

- **SHALL** populate `Slot.serviceType.text` with a practice defined slot type description, and where available `Schedule.serviceCategory.text` with a practice-defined schedule type description (may be called session name or rota type) - the slot and schedule description fields **SHOULD** be the same as those visible in the NHS App

- **SHALL** meet {{pagelink:Home/Build/FHIR-Resource-Guidance.page.md}} populating all fields for `Schedule` and `Slot` where data is available, excluding those listed below

- **SHALL NOT** populate the `specialty` field on `Schedule` or `Slot`  

#### Error handling ####

The provider system **SHALL** return an error if:

- the time period defined by `start` and `end` parameters is greater than a two-week period
- the `status` parameter is absent or is present with a value other than `free`
- the `_include=Slot:schedule` is absent

**SHALL** return a {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Profile--GPConnect-OperationOutcome-1}} resource that provides additional detail when one or more parameters are corrupt or a specific business rule/constraint is breached.

Refer to {{pagelink:error-handling}} for details of error codes.

## Examples ##

### Example - Searching with all parameters ###

#### Request ####

The example below shows a typical search for free slots request from a consumer system.

The consumer system is:
  
- sending all search parameters
- and searching on date

```http
GET /Slot?status=free
  &start=ge2017-09-02
  &end=le2017-09-15
  &_include=Slot:schedule
  &_include:recurse=Schedule:actor:Practitioner
  &_include:recurse=Schedule:actor:Location
  &_include:recurse=Location:managingOrganization
  &searchFilter=https://fhir.nhs.uk/Id/ods-organization-code|A1001
  &searchFilter=https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1|gp-practice
```
<br></br>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> New lines and spacing have been added for readability in the example above. These are not included in an actual request.
</div>

#### Response ####

The example response includes two Slot resources matching the search crieria and associated Schedule, Location, Practitioner and Organization resources.

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
            "text": "GP Appointment"
          }
        ],
        "schedule": {
          "reference": "Schedule/14"
        },
        "status": "free",
        "start": "2017-09-15T11:30:00+01:00",
        "end": "2017-09-15T11:40:00+01:00"
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
        "start": "2017-09-15T11:40:00+01:00",
        "end": "2017-09-15T11:50:00+01:00"
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
          "start": "2017-09-15T09:00:00+01:00",
          "end": "2017-09-15T12:00:00+01:00"
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
        "telecom": [
          {
            "system": "phone",
            "value": "03003035678",
            "use": "work"
          }
        ],
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
        "address": [
          {
            "line": [
              "Trevelyan Square",
              "Boar Ln"
            ],
            "city": "Leeds",
            "district": "West Yorkshire",
            "postalCode": "LS1 6AE"
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "03003035678",
            "use": "work"
          }
        ]
      }
    }
  ]
}
```

### Example - Searching with the minimum parameters ###

#### Request ####

The example below shows a typical search for free slots request:

- sending mandatory and required parameters only
- and searching on date and time

```http
GET /Slot?status=free
  &start=ge2019-03-29T12:00:00+00:00
  &end=le2019-04-01T17:00:00+01:00
  &_include=Slot:schedule
  &searchFilter=https://fhir.nhs.uk/Id/ods-organization-code|A1001
  &searchFilter=https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1|gp-practice
```
<br></br>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> New lines and spacing have been added for readability in the example above. These are not included in an actual request.
</div>

#### Response ####

The example response includes two Slot resources matching the search criteria, and associated Schedule and Organization resources.

This example also shows the absence of a Practitioner resource.  This may happen where a provider organisation has not yet assigned a named practitioner to an appointment schedule.

The Organization resource is returned in this Bundle despite the Organization _include parameter not being sent (this is a {{pagelink:known-issues}}.

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
            "text": "GP Appointment"
          }
        ],
        "schedule": {
          "reference": "Schedule/14"
        },
        "status": "free",
        "start": "2019-03-29T11:30:00+01:00",
        "end": "2019-03-29T11:40:00+01:00"
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
        "start": "2019-03-29T11:40:00+01:00",
        "end": "2019-03-29T11:50:00+01:00"
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
          }
        ],
        "planningHorizon": {
          "start": "2019-03-29T09:00:00+01:00",
          "end": "2019-03-29T12:00:00+01:00"
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
        "address": [
          {
            "line": [
              "Trevelyan Square",
              "Boar Ln"
            ],
            "city": "Leeds",
            "district": "West Yorkshire",
            "postalCode": "LS1 6AE"
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "03003035678",
            "use": "work"
          }
        ]
      }
    }
  ]
}
```

### Example - No slots returned ###

#### Request ####

The example below shows a typical search for free slots request:

- sending all request parameters
- and searching on date

```http
GET /Slot?status=free
  &start=ge2017-10-01
  &end=le2017-10-07
  &_include=Slot:schedule
  &_include:recurse=Schedule:actor:Practitioner
  &_include:recurse=Schedule:actor:Location
  &_include:recurse=Location:managingOrganization
  &searchFilter=https://fhir.nhs.uk/Id/ods-organization-code|A1001
  &searchFilter=https://fhir.nhs.uk/STU3/CodeSystem/GPConnect-OrganisationType-1|gp-practice

```
<br></br>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> New lines and spacing have been added for readability in the example above. These are not included in an actual request.
</div>
#### Response ####

The example response shows an empty Bundle as no slots were found matching the search criteria.

```json
{
  "resourceType": "Bundle",
  "type": "searchset",
  "entry": []
}
```
---