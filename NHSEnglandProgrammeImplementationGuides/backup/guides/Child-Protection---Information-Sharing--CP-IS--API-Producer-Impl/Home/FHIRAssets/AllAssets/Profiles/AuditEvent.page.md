## {{page-title}}

The profile is provided for implementation guidance:
- a returned AuditEvent will not reference the profile in the Resource.meta.

## Conformance Rules

A searchset Bundle will be returned on the GET /[Resource] interaction ({{pagelink:Home/Design/Interactions.page.md}}). 

The Bundle will contain 0 to Many AuditEvent resources matching the NHSNumber searchParameter and 0 to Many resources matching any relevant _include resources.

The base <a href="http://hl7.org/fhir/r4/auditevent.html" class="external">AuditEvent</a> structureDefinition is available at hl7.org/fhir
