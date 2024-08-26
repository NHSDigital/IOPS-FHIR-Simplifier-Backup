## {{page-title}}

### FHIR resources
Provider systems **MUST** return a minimal set of structured data along with the HTML content as follows:

| FHIR resource(s) | Composition section |
| --- | --- |
| `Patient` | Subject |
| `Practitioner` | User |
| `Organization` | Custodian |
| `Device` | Author* |

*As the composition is machine-generated the concept of a single Author does not make logical sense. It is expected that the Author field will be populated with the details of the software system which generated the composition.

### Demographic cross checking
Consumer systems **MUST** compare the returned structured patient demographic data (supplied by the provider system as structured data) against the demographic data held in the consumer system.

If differences exist then the consumer system **MUST** show an alert/warning and provide details of which fields/values are different between the two systems.

The following data **MUST** be cross checked between consumer and returned provider data. Any differences between these fields **MUST** be brought to the attention of the user.

| Item | Resource element |
| --- | --- |
| Family Name | `Patient.name.family` |
| Given Name | `Patient.name.given` |
| Gender | `Patient.gender` |
| Birth Date | `Patient.birthDate` |
| GP Practice Code | `Patient.managingOrganization` |
| Deceased Date Time | `Patient.deceased[x](deceasedDateTime)` |

Additionally, the following data **MAY** be displayed if returned from the provider to assist a visual cross check and for safe identification but should not be part of the automatic comparison.

- Address and Postcode
- Contact (telephone, mobile, email)
- Responsible GP Code and Name
- GP Practice Name and Address
Where a patient is flagged on the GP clinical system as sensitive (and as such the GP practice must not identify that the patient is registered at this location), the provider system **MUST NOT** return any clinical records and instead return the error Patient not found.

Where a patient is flagged on the Personal Demographics Service (PDS) as sensitive (and as such it is not possible to confirm their registered GP practice), the consumer system **MUST NOT** use GP Connect.