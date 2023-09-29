## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Referencing an `Organization resource is likely to be more useful than a person, as a Practitioner resource, as people’s work patterns and employers may be variable while the care setting organisation will be constantly available.

When referencing an organisation - the following must be provided:

- `Oraganization.contact.name`
- `Organization.contact.telecom`
- `Organisation.identifier.odsOrganizationCode` or `Organization.identifier.odsSiteCode`

Where the organisation is an Acute Trust, an ODS Site Code may be more useful than the parent Trust-wide ODS organisation code.


<h5><ins>Example</ins></h5>

```xml
<informationSource>
    <reference value="oraganization-1234" />
</informationSource>
```

---