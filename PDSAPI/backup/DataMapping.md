### Data Mapping

This page gives the mapping of data items defined in the PDS domain to FHIR

| PDS Object/Data Item | PDS Cardinality | FHIR Target (R4) | Notes |
|----------------------|-----------------|------------------|-------|
| Miscellaneous Data | 0..1 |  | |
| Matching Level | 1..1 | Bundle.entry.search.score | |
| Patient Identifier | 1..1 | Patient.identifier | |
| NHS Number | 1..1 | Patient.identifier (NHS Number) [slice].value | |
| Serial Change Number | 1..1 |  | |
| Serial Change Number | 1..1 | Patient.meta.versionId | |
| Person Name | 0..* | Patient.name | |
| Name Type | 1..1 | Patient.name.HumanName.use | |
| Family Name | 0..1 | Patient.name.HumanName.family | |
| First Given Name | 0..1 | Patient.name.HumanName.given | |
| Other Given Name(s) | 0..1 | Patient.name.HumanName.given | |
| Name Prefix | 0..1 | Patient.name.HumanName.prefix | |
| Name Suffix | 0..1 | Patient.name.HumanName.suffix | |
| Business Effective From Date | 0..1 | Patient.name.HumanName.period.start | |
| Business Effective To Date | 0..1 | Patient.name.HumanName.period.end | |
| Person Gender | 0..1 |  | |
| Person Gender Code | 1..1 | Patient.gender | |
| Person Birth Date | 0..1 |  | |
| Person Birth Date | 1..1 | Patient.birthDate | |
| Delivery Time | 0..1 | https://www.hl7.org/fhir/extension-patient-birthtime.html | |
| Place Of Birth | 0..1 | https://www.hl7.org/fhir/extension-patient-birthplace.html | |
| Town | 0..1 | extension-patient-birthplace.Address.city | |
| County or District | 0..1 | extension-patient-birthplace.Address.district | |
| Country | 0..1 | extension-patient-birthplace.Address.country | |
| Person Death Date | 0..1 |  | |
| Person Death Date | 1..1 | Patient.deceased[x].dateTime | |
| Time of Death | 0..1 |  | |
| Status of Death Notification | 1..1 | Extension-UKCore-DeathNotificationStatus-1.extension (deathNotificationStatus).valueCodeableConcept | |
| Person Address | 0..* | Patient.address | |
| Address Type | 1..1 | Patient.address.use | |
| Address Line | 0..5 | Address.line | |
| Postcode | 0..1 | Address.postalCode | |
| PAF Key | 0..1 | Extension-UKCore-AddressKey | |
| Business Effective From Date | 0..1 | Address.period.start | |
| Business Effective To Date | 0..1 | Address.period.end | |
| Telecommunication Address | 0..* | Patient.telecom | |
| Telecom Usage | 1..1 | Patient.telecom.ContactPoint.use | |
| Communication Contact Method | 1..1 | Patient.telecom.ContactPoint.system | |
| Communication Contact String | 1..1 | Patient.telecom.ContactPoint.value | |
| Business Effective From Date | 0..1 | Patient.telecom.ContactPoint.period.start | |
| Business Effective To Date | 0..1 | Patient.telecom.ContactPoint.period.end | |
| Person Confidentiality | 0..1 |  | |
| Information Sensitivity Indicator | 1..1 | Patient.meta.security | |
| Contact Preferences | 0..1 | Extension-UKCore-ContactPreference | |
| Preferred Contact Method | 0..1 | Extension-UKCore-ContactPreference | |
| Preferred Contact Times | 0..1 | Extension-UKCore-ContactPreference | |
| Preferred Written Communication Format | 0..1 | Extension-UKCore-ContactPreference | |
| Language Communication | 0..1 | Extension-UKCore-NHSCommunication | |
| Language | 1..1 | Extension-UKCore-NHSCommunication | |
| Interpreter Required Indicator | 1..1 | Extension-UKCore-NHSCommunication | |
| Primary Care Registration | 0..* | Patient.generalPractitioner. Organization.type | |
| Patient Care Provision Type | 1..1 | Patient.generalPractitioner. Organization.type | |
| Primary Care Identifier | 1..1 | Patient.generalPractitioner. Organization.identifier | |
| Baby Tracing Data | 0..1 | patient.multipleBirth | |
| Birth Order | 1..1 | patient.multipleBirth.boolean | |
| Birth Order | 1..1 | patient.multipleBirth.integer | |
| Pharmacy Data | 0..* | Extension-CareConnect-NominatedPharmacy-1 | |
| Pharmacy Identifier | 1..1 | Extension-CareConnect-NominatedPharmacy-1.valueReference.organization.identifier | |
| Pharmacy type | 1..1 | Extension-CareConnect-NominatedPharmacy-1.valueReference.organization.type | |
 |