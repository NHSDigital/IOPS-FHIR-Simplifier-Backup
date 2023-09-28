## `identifier`

<b>Definition:</b>

| FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description | Professional Code | Prescribing Code |
|--|--|--|--|--|--|--|
| https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code |  |  | G[67]NNNNNN | NHS BSA Spurious Code [GENERAL MEDICAL PRACTITIONER PPD CODE](https://datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html) | No | Yes |
| https://fhir.nhs.uk/Id/sds-role-profile-id | 1.2.826.0.1285.0.2.0.67 | | 12 digits | SDS Role Profile Code | No | No |

The *SDS Role Profile Code* should be sourced from NHS Identity (SmartCard), this is also held within the Spine Directory Service LDAP database.

Holds *NHS BSA spurious codes* which are role specific *Doctor Index Number (DIN)*) codes. *NHS BSA spurious codes* are issued when a doctor issues medication outside of their normal role, normally at another organisation.

---

