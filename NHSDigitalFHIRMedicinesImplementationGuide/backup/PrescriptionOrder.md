## {{page-title}}


| FHIR Exchange | API | Event Type | FHIR (Bundle) Message Definition |
|--
| FHIR Messaging  | [POST /$process-message](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-send-prescription-order-message) | `prescription-order` | {{pagelink:prescription-order}} |

<br>

The `prescription-order` FHIR Message is sent to the EPS [$process-message](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir#api-Prescribing-sendMessage) endpoint. The contents of this message are defined in {{pagelink:prescription-order}}

{{render:process-message-duplicate-2}}

### Additional Notes

#### Prescription Type (courseOfTherapyType)

The `prescription-order` **MUST NOT** mix `continuous-repeat-dispensing` prescriptions and  `acute` / `continuous` prescriptions in the same order.

#### Maximum number of repeat prescriptions(repeatInformation.numberOfRepeatPrescriptionsAllowed)

If present the maximum number of repeat prescriptions must be identical for all items on a prescription.

#### Prescription Authorisation Expiry (repeatInformation.authorisationExpiryDate)

The order authorisation expiry date is the earliest prescription expiry date found in the order. If separate Authorisation Expiry dates are required, then those prescriptions must be sent individually.

If present the authorisation expiry date must be identical for all items on a prescription.

#### Prescription Validity Period (dispenseRequest.validityPeriod)

This **MUST** be identical for all items in the prescription order.

#### Prescription Duration (dispenseRequest.expectedSupplyDuration)

This **MUST** be identical for all prescriptions within the order and **MUST** be specified in days.

<br>