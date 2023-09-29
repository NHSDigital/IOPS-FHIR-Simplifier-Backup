### {{page-title}}

| FHIR Exchange | API | FHIR Operation Definition |
|--
| FHIR Operation  | [POST /Task/$release](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Dispensing-release) | {{pagelink:release-duplicate-2.md}} |

<br>

Is the methods the pharmacy will use to retrieve prescriptions from EPS. Both methods use a common {{pagelink:release-duplicate-2.md }} operation and will return a FHIR Bundle consisting of 0..* `prescription-order` messages.

#### Nominated Pharmacy Release Request

{{render:nominatedreleaserequest}}

#### Patient Release Request

{{render:patientreleaserequest}}

### Build Notes

- {{pagelink:DownloadPrescriptionfromEPS.md}}