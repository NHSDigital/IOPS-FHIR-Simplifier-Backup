---
subject: https://fhir.nhs.uk/England/SearchParameter/England-Extension-OrganisationRole-RoleCode
issue: England-Extension-OrganisationRole-RoleCode
---
## {{page-title}}

Usage:
- This SearchParameter allows the searching for Organization instance, where the Extension-England-OrganisationRole is present and where the <code>active</code> element is true
- This returns the <code>roleCode</code> element
- The fhirPath expression is: <code>Organization.extension('https://fhir.nhs.uk/England/StructureDefinition/Extension-England-OrganisationRole').extension('roleCode').value</code>

{{page:Home/FHIR-Assets/AssetWithoutExamples.page.md}}

---