## {{page-title}}

The profile is provided for implementation guidance:
- a returned CareTeam will not reference the profile in the Resource.meta.

## Conformance Rules

A searchset Bundle will be returned on the GET /[Resource] interaction ({{pagelink:Home/Design/Interactions.page.md}}). 

The Bundle will contain 0 to Many CareTeam resources matching the NHSNumber searchParameter.

'Type of Child Protection care plan in place' is coded in the CareTeam.category element. CP-IS applications SHALL use SNOMED CT codes from [ValueSet England-ChildProtectionPlan]({{pagelink:Home/FHIRAssets/AllAssets/ValueSets/ValueSet-EnglandChildProtectionPlan.page.md}}) in CareTeam.category

The base <a href="http://hl7.org/fhir/r4/careteam.html" class="external">CareTeam</a> structureDefinition is available at hl7.org/fhir
