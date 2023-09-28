## `identifier`

<b>Definition:</b>

At least one patient identifier, **MUST** be provided.

Where a traced NHS number is available for a patient this MUST be included. In general an untraced NHS Number **MUST** not be used, if an untracted NHS Number is used the extension https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberVerificationStatus **MUST** be used.

| Name | FHIR identifier | OID/HL7v3 | HL7v2 ITK | Format | Description |
|--|--|--|--|--|--|
| NHS Number | https://fhir.nhs.uk/Id/nhs-number | 2.16.840.1.113883.2.1.4.1 |  NHS | NNNNNNNNNN | NHS Number allocated to the patient in England and Wales  |
| CHI Number | | 2.16.840.1.113883.2.1.3.2.4.16.53 | | NNNNNNNNNN | CHI Number allocated to the patient in Scotland |
| NHS Logon ID | https://fhir.nhs.uk/Id/nhs-login-sub | | | uuid | NHS Login unique identifer which is referred to as sub in NHS Login (OpenID) |

<br />

Local identifiers such as MRN **MUST** include a *system* which identifies NHS provider/assigning authority.

---