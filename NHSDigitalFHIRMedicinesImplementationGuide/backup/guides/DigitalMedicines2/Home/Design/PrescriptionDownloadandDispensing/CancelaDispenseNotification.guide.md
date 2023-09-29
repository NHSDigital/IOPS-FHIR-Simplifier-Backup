## {{page-title}}

| FHIR Exchange | API | FHIR Resource Profile |
|--
| FHIR RESTful  | [PUT /Task/(dispense-notification-reference)](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-withdraw) | {{pagelink:NHSDigital-Task-duplicate-2}} |

The *dispense-notification-reference* is taken from the `Bundle.identifier.value` of the dispense-notification which is to be cancelled.

#### Example

`PUT /Task/334a3195-1f6c-497a-8efe-d272ca9c4e38`

Payload:

- {{pagelink:TaskCancelDispenseNotification-duplicate-2}}


