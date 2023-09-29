## How to use this implementation guide

This section provides a <a href="#P1">site map</a> of this implementation guide, describes the page contents and the intended audience. 

## Implementation Guide Format and Structure

The table below gives the reader of this implementation guide guidance about the structure of the guide and an indication of the purpose and intended audience of the sections and pages the guide contains. The intended audience is included to illustrate which type of reader the page is primarily aimed at and of course does not exclude other types of readers from reviewing and feeding back to the team producing the implementation guide.   

|Page|Subpage(s)|Description and purpose|Usage|Intended Audience|
|--|--|--|--|--|
|Home||This is the starting point for readers and should be the page that is used when a link is provided to the Implementation Guides|Will be present||
|Introduction||This gives a brief overview of the implementation guidance around things such as: uses cases, scope etc. |Will be present||
||How to use this implementation guide|This gives a generated site map of the implementation guide and guidance to help them understand the implementation guide |Will be present ||
||Release notes|Gives the change history and any additional information to help the reader understand the changes to the guide. The latest changes will be added to the top of the page.|Will be present||
||Guide versioning|Details versioning of implementation guides and what the different stages are, links to a separate guide|Will be present||
||Glossary|A glossary of terms and acronyms used, links to a separate guide|Will be present||
|FHIR Assets||A section that has subpages for each of the FHIR assets, not all FHIR assets are used for all implementations|Will be present|Clinical,Business,Architect,FHIR,Developer|
||Profiles|The page will contain the Profiles for this implementation guide|Will be present|Clinical,Business,Architect,FHIR,Developer|
||Extensions|The page will contain the Extensions used by this implementation guide|Will be present|Clinical,Business,Architect,FHIR,Developer|
||CodeSystems|The page will contain the CodeSystems for this implementation guide|Will be present|Clinical,Business,Architect,FHIR,Developer|
||ValueSets|The page will contain ValueSets for this implementation guide|Will be present|Clinical,Business,Architect,FHIR,Developer|
||ConceptMaps|The page will contain the ConceptMaps for this implementation guide|May be present|Clinical,Business,Architect,FHIR,Developer|
||SearchParameters|The page will contain the SearchParameters for this implementation guide|May be present|Business,Architect,FHIR,Developer|
||CapabilityStatements|The page will contain the CapabilityStatements for this implementation guide|May be present|Clinical,Business,Architect,FHIR,Developer|
||All Assets|This page is a navigation page and lists the FHIR Asset types|Will be present||
|Design||This section details the design of the FHIR implementation/ use case, it will detail such things as the interactions, transport used, how the data is exchanged etc. |Will be present|Clinical,Business,Architect,FHIR,Developer|
||Design overview|An overview of the design approach|Will be present||
||Data Mapping|The mapping of the data to be exchanged to the FHIR assets. This may be a defined national dataset or just an agreed list of data items for a first of type |May be present|Business,FHIR|
||Interactions|This page will contain text and diagrams which describe how the systems/users/device interact with each other|Will be present|Clinical,Business,Architect,FHIR,Developer|
|Build||This section is about how to build a system or API using this implementation guide|Will be present||
||API usage|This page is used to describe how the API is used in a real life environment|May be present|Clinical,Business,Architect,FHIR,Developer|
||Error handling|Describes any error handling that is applicable for the implementation guide|May be present|Clinical,Business,Architect,FHIR,Developer|
||Query types|The query types supported by this implementation guide, only applicable for REST|May be present|Clinical,Business,Architect,FHIR,Developer|
||Operation responses|This page is used to describe the search operations supported by the API and their responses.|May be present|Clinical,Business,Architect,FHIR,Developer|
|Examples||This page gives an overview of the examples section.|Will be present|Clinical,Business,Architect,FHIR,Developer|
||Example [X]|A page which contains a FHIR example structure. This may be just a single FHIR resource or multiple resources for example a Bundle. The example may be in JSON or XML or both depending on the format used by the implementation|Will be present|Clinical,Business,Architect,FHIR,Developer|
|Authentication||This page needs a brief overview of the authentication section|May be present|Architect,Developer|
|Downloads|This page provides link(s) to download artefacts that may be useful to help with developments such as NPM packages for validation|Will be present|Clinical,Business,Architect,FHIR,Developer|
|Help and support|This page gives contact details for help and support|Will be present|Clinical,Business,Architect,FHIR,Developer|

## Intended Audience

This section describes the type of audience that the section or page is targeted at (if any) where none is stated then the page should be seen as a general page for every reader.

|Audience|Description|
|--
|Clinical|Someone who is reviewing the implementation guide from a clinical perspective, including clinical safety, clinical pathway and informatics; as a clinical professional involved in initial implementations or further roll-out approaches|
|Business|Someone who is reviewing the implementation guide from a business process perspective; as a business analyst looking into workflow and the impact on existing business processes|
|Architect|Someone who is reviewing the implementation guide from an architectural perspective; as a solution architect looking into how this implementation will fit in with existing systems and interfaces |
|FHIR |Someone who is reviewing the implementation guide from a standards perspective; as a person with FHIR knowledge involved in reviewing the implementation guide for compliancy with the FHIR standard or alignment with other FHIR implementations|
|Developer|Someone who is reviewing the implementation guide from a development perspective, the developer who will be coding or involved in the building of the API or system|
|Other|Someone looking into the contents of the implementation guide for any other reason, for example as part of their education or a research project. This type of audience is implied and not shown in the table below.|


<h2 id="P1">Site Map</h2>

{{index:root}}



