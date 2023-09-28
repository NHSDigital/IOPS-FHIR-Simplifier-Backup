## `informationSource`

The resource being referenced SHALL conform to one of the following:
- {{pagelink:Profile-Organization-94604}}
- {{pagelink:Profile-Patient-88961}}
- {{pagelink:Profile-Practitioner-10758}}
- {{pagelink:Profile-PractitionerRole-55046}}
- {{pagelink:Profile-RelatedPerson-51006}}

Referencing an organisation is likely to be more useful than a person. Individual work patterns and/or employer may change while the care setting organisation is likely to be more static and relevant within historic instances of this resource.

When referencing an organisation - the following SHALL be provided:

- `Organization.contact.name`
- `Organization.contact.telecom`
- `Organization.identifier.odsOrganisationCode` or `Organization.identifier.odsSiteCode`

Where the organisation is an Acute Trust, an ODS Site Code MAY be more useful than the parent Trust-wide ODS organisation code.

---
