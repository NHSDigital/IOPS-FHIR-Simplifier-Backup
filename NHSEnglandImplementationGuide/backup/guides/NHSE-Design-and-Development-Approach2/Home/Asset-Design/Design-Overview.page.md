# {{page-title}}


## FHIR Assets

This section documents the approach used by IOPS to produce and maintain the NHS England Implementation Guides and the NHS England FHIR assets. It will be updated and matured in line with decisions taken during the Clinical and Technical Assurance process. This documentation is aimed at the technical reader and is included as reference material. The approach is based on the design principles.

### Changes to FHIR Profiles and conformance assets
- These are hosted on the GitHub project [here](https://github.com/NHSDigital/NHSEngland-FHIR-ImplementationGuide).
- Each folder contains resources of a specific type. In particular, the structuredefinitions folder contains the FHIR profiles and extensions, the valuesets and codesystems folders contain the valuesets and codesystems used across NHSE programmes, and the CapabilityStatement folder contains resources which define which profiles to validate against in a specific context.
- The IOPS change control process is [here](https://simplifier.net/guide/nhs-england-design-and-development-approach/approach2-home-management-development-and-release-management-change-control?version=current).
- If approved, changes to FHIR assets will be made in a branch with the same name as the JIRA ticket from which the request originated (e.g. AEA-3019). This links changes to the original request for auditing.
- To release a package using the changed assets, the branch needs to be merged into the 'main' branch. This will be done through a Pull Request (PR), which can only be merged after receiving approval from the IOPS team.
- Once merged into the main branch, the commit will be tagged with the package number and marked as pre-release, e.g. See [here](https://github.com/NHSDigital/NHSEngland-FHIR-ImplementationGuide/tags). This allows easy comparison of changes between releases.
- A mirrored release of the npm package will then be created, incrementing the patch number and corresponding releases of the NHSE Implementation Guide.
- The NHS England package guidance is [here](https://simplifier.net/guide/nhs-england-design-and-development-approach/home-management-version-management-package-versioning?version=current).

## Conformance

The NHS England IG conforms to the [HL7 FHIR® specification Release 4](https://hl7.org/fhir/R4/index.html) and its assets are profiles derived from the corresponding UK Core Profiles. In addition, the NHS England IG also conforms to [UK Core STU3](https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence?version=current).

## Design Principles

### Key Principle

FHIR assets shall be England specific and shall be capable of representing the requirements of NHS England. The assets shall only be created where there is a valid requirement to further constraint the UK Core assets or in the case of extensions to extend the UK Core. 

### Other Principles

#### Reference DataType

References in profiles shall use the FHIR base resource name only and there will be clear documentation on each profile page to explain how this relates to profiles (NHS England or UK Core).

Vendors shall build to UK Core profiles in data exchanges see the section on conformance in [NHS England IG](https://simplifier.net/NHS-England-Implementation-Guide/~guides).


#### Extensions

Extension will be constrained (hard coded) into profiles to profiles after agreement during Clinical and Technical assurance which is the process for extension approval.

The Implementation Guide for the NHS England IG will include an Extension Library page, which will list extensions and their corresponding NHS England IG profiles. There is no requirement to profile HL7 extensions locally. Where a HL7 extension is identified as in scope, a link to it will be added on the Extension Library page under HL7 Common Extensions.

Read more about [FHIR Extensions](https://www.hl7.org/fhir/r4/extensibility.html) and [Extension Design.](https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/Asset-Design/Extension-Design?version=current)

#### Cardinalities
FHIR resource element cardinalities will only be amended, if clinical justifications are agreed during Clinical and Technical assurance.
No elements will be removed unless deemed clinically unsafe following consultation and agreement during Clinical and Technical assurance.
Read more about FHIR resource [cardinalities.](http://hl7.org/fhir/r4/profiling.html#cardinality)

#### Slicing
SHALL only be used where it enforces structure in a profile, for example
for a ValueSet binding
for the representation of an identifier in a list, such as a patient's NHS number
Slicing SHALL be Open e.g. one or more additional slices can be added.
Read more about [Slicing](https://www.hl7.org/fhir/r4/profiling.html#slicing) in FHIR.

#### Must Support
We inherit 'Must Support' flags from UK Core, and any that have been added in NHSE IG come from NHSD IG and will only be used when there is a requirement arising from a use case identified during Clinical and Technical assurance.
Read more about "Must Support" in FHIR.

#### ValueSets
Binding Strengths
The ValueSet binding strength SHOULD be decided as part of the Clinical and Technical Assurance, but the general philosophy is as the following:

- required - Used only when defined as 'required' by the FHIR standard, or when decided as part of the Clinical and Technical Assurance.
- extensible - All ValueSets SHOULD be set to 'extensible', where not defined as 'required' by the FHIR standard, or 'preferred' by the NHSE IG standard.
- preferred - Used when the ValueSet contains SNOMED CT or dm+d concepts due to their inherent complexities, or when decided as part of the Clinical and Technical Assurance.
- example - Decided as part of the Clinical and Technical Assurance.
Read more about [ValueSets](https://www.hl7.org/fhir/r4/terminologies.html#valuesets) and [ValueSet bindings](https://www.hl7.org/fhir/r4/terminologies.html#strength) in FHIR.

#### Validation
All FHIR assets SHALL be validated before being publicly available. See [Validation of Implementations](https://simplifier.net/guide/nhs-england-design-and-development-approach/Home/Conformance---Dependencies/Validation-of-Implementations.page.md?version=current) for more details.

#### FHIR Asset Spelling
FHIR assets use the American-English spelling in asset names, for example Organization. The NHS England IG approach is to use American-English for any Profile, Extension, ValueSet, and CodeSystem name, as well as when these are referenced within the Implementation Guide. Otherwise, the use of British-English spelling shall we used.

---

