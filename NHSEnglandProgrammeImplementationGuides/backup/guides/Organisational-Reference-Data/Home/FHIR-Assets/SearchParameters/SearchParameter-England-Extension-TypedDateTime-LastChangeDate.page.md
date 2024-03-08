---
subject: https://fhir.nhs.uk/England/SearchParameter/England-Extension-TypedDateTime-LastChangeDate
issue: England-Extension-TypedDateTime-LastChangeDate
---
## {{page-title}}

Usage:
- This SearchParameter allows the searching for Organization instance, where the Extension-England-OrganisationRole is present and where the <code>active</code> element is true
- This returns the <code>dateTime</code> element
- The fhirPath expression is: <code>Organization.extension('https://fhir.nhs.uk/England/StructureDefinition/Extension-England-TypedDateTime').extension('dateTime').value</code>

{{page:Home/FHIR-Assets/AssetWithoutExamples.page.md}}

---