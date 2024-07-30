## {{page-title}}

### FHIR Assets Versioning
 
The versioning for published assets will use the <a href="http://semver.org/" Target="_blank"> Semantic Versioning Standard</a>. The major and minor versions will be visible, and the patch version MAY also be exposed.
Version numbers held in profiles and resource instances SHALL therefore be in the following form:-

-  MAJOR.MINOR.PATCH – e.g. 1.0.2
or
- MAJOR.MINOR - e.g. 1.0

### Definitions of Change Types
There is no real way to determine whether a UK Core change is breaking or not unless you can get agreement with every implementer of the UK Core. This is practically impossible to do, so the following sections are to give a brief overview of the sort of changes that might be seen as breaking changes and should not be seen as definitive. 
#### Major Change
This is a breaking change, and as such, implementers will need to understand the changes that have been made in the new version, and make changes to their implementations, if required, as such a change is not backwards compatible. An example could be :-
- Addition of new mandatory element(s) in a profile
- ValueSet binding increasing in strength, e.g from preferred to extensible
#### Minor Change
A minor change is defined as a backwards compatible change which is not expected to break existing implementations. Examples include :-
- Addition of new optional element(s) in a profile
- Addition of new operations whose names do not clash with existing operations
#### Patch
This is defined as a version in which backwards compatible bug fixes are made that do not change the original intent of the asset. An example could be :-
-  Correcting typos in the short description of an element in a FHIR profile
- fixing broken ValueSet bindings

The UK Core is released as a pre-release for comment before an actual release, this will be with full change history for the changes applied so that implementers can agree the versioning that has been applied to the FHIR assets.

### Atifact Versioning Policy
The UK Core follows the <samp>metadata</samp> <a href="https://build.fhir.org/ig/HL7/crmi-ig/branches/master/artifact-lifecycle.html#artifact-versioning-policy">versioning policy</a>, which indicates that non-substantive changes to the metadata elements of an artifact may be made without incrementing the version number. When this occurs, the date element SHALL be updated.

### Publication of a version within a UK Core asset
Version data will be carried in the version element for all assets.   
These assets are :-
- <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/ProfilesandExtensions/ProfilesIndex.page.md?version=current" Target="_blank"> StructureDefinitions</a> 
-  <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/ProfilesandExtensions/ExtensionLibrary" Target="_blank"> Extensions</a>
- <a href="https://simplifier.net/guide/uk-core-implementation-guide/Home/Terminology/ValueSetsandCodeSystems" Target="_blank"> ValueSets/CodeSystems</a>
- <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide/Home/Terminology/ConceptMaps" Target="_blank"> ConceptMaps</a>   

The version information is maintained by the <a href="https://simplifier.net/HL7FHIRUKCoreR4/~team" Target="_blank"> UK Core Development team</a> in line with the Semantic Versioning Standard outlined above. Thus, for a StructureDefinition, this could read:

````xml
<StructureDefinition xmlns="http://hl7.org/fhir">
  <id value="UKCore-Patient" />
  <url value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient" />
  <version value="2.1.0" />
````   
For a ValueSet, this could read:

````xml
<ValueSet xmlns="http://hl7.org/fhir">
<id value="UKCore-MedicationForm"/>
<url value="https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm"/>
<version value="2.0.0"/>
````
Further information about both FHIR asset creation and maintenance is available on the {{pagelink:FHIRAssetDesign}} page. 


---

