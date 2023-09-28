### Overview
This section details the version management approach used with the NHS England Implementation Guides, NHS England Implementation Guides packages and FHIR assets. The approach differs for each of these items and so is documented in separate sections.

### FHIR Assets Versioning
All FHIR Assets produced for the NHS England IG will be versioned during development using <a href="https://git-scm.com/" Target="_blank"> Git</a> and will follow the standard <a href="https://guides.github.com/introduction/flow/" Target="_blank"> GitFlow model</a>. The version number of each FHIR Asset will reflect the overall version of the release that the asset belongs to. This is in line with the approach used in HL7 FHIR R4. 

The version information is maintained by the IOPS team in line with the Semantic Versioning Standard outlined above. For example, if the overall release version number is v1.0.0, then the below example will show what the version would be like for different assets.

For a StructureDefinition, this would read:

````xml
<StructureDefinition xmlns="http://hl7.org/fhir">
  <id value="England-Patient" />
  <url value="https://fhir.nhs.uk/StructureDefinition/England-Patient" />
  <version value="1.0.0" />
````
For a ValueSet, this would read:

````xml
<ValueSet xmlns="http://hl7.org/fhir">
<id value="England-VaccineCode"/>
<url value="https://fhir.nhs.uk/ValueSet/England-VaccineCode"/>
<version value="1.0.0"/>
````

A referenced URL could also incorporate a version number within it. For example:

<code>https://fhir.nhs.uk/StructureDefinition/England-Patient|1.0.0</code>

This is illustrated below:

````xml
<Patient xmlns="http://hl7.org/fhir">
    <id value="P123" />
    <meta>
        <profile value="https://fhir.nhs.uk/StructureDefinition/England-Patient|1.0.0" />
    </meta>
````

### Definitions of Change Types
There is no real way to determine whether a NHS England IG change is breaking or not unless you can get agreement with every implementer of the NHS England IG. This is practically impossible to do, so the following sections are to give a brief overview of the sort of changes that might be seen as breaking changes and should not be seen as definitive. 
#### Major Change
This is a breaking change, and as such, implementers will need to understand the changes that have been made in the new version, and make changes to their implementations, if required, as such a change is not backwards compatible. An example could be :-
-  Addition of new mandatory element(s) in a profile
#### Minor Change
A minor change is defined as a backwards compatible change which is not expected to break existing implementations. Examples include :-
-  Addition of new optional element(s) in a profile
-  Addition of new operations whose names do not clash with existing operations
#### Patch
This is defined as a version in which backwards compatible bug fixes are made. An example could be :-
-  Correcting typos in the short description of an element in a FHIR profile

The NHS England IG is released as a pre-release for comment before an actual release, this will be with full change history for the changes applied so that implementers can agree the versioning that has been applied to the FHIR assets.

### Semantic Versioning
Given a version number MAJOR.MINOR.PATCH, increment the:

MAJOR version when you make incompatible changes, MINOR version when you add functionality in a backwards-compatible manner, and PATCH version when you make backwards-compatible bug fixes. Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

### Pre-Release Labels
These labels will be taken from the GDS development process stages, and will be one of:

- **Discovery**: a Feasibility study. A 'No code' development. Designed to find out what users are trying to achieve, any constraints, improvement opportunities

- **Alpha**: Develop prototypes and test with users. Could be minimal functionality and potentially prototypes for any options to determine which is best

- **Private Beta**: Working version and test with invited users. Handle real transactions and work at scale. ‘Invite only’ or regional. Must Pass assessment by business and technical SME’s

- **Public Beta**: All users can participate. Version unlikely to change substantially, but still needs further testing by a wider group of implementors before becoming live

- **Live**: The live phase is about supporting the service in a sustainable way, and continuing to iterate and make improvements

- **Retiring**: Implementors notified that the service is discontinued and not to be used for new developments


### Instance Conformance Identification
For some information flows, there is a requirement to identify which NHSE IG profile(s) an instance being exchanged between healthcare IT systems conforms to. This could be for the purpose of validation of the instance against the profile definition and/or for conformance testing. This profile conformance is declared using the profile.meta element. The element carries the profile URL appended with the version information. 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Most implementations will use NPM Packages for validation and therefore the use of this approach is not mandated when using NHSE IG profiles.   </div>

More information about NPM packages is available on the
[package versioning page.](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Management/Version-Management?version=current#Package-Versioning)

The format is: 'URL' "\|" 'version'
For example:

<code>https://fhir.nhs.uk/R4/StructureDefinition/England-Patient|1.0.0</code>

This is illustrated below:

````xml
<Patient xmlns="http://hl7.org/fhir">
    <id value="P123" />
    <meta>
        <profile value="https://fhir.hl7.org.uk/StructureDefinition/England-Patient|1.0.0" />
    </meta>
````
---
