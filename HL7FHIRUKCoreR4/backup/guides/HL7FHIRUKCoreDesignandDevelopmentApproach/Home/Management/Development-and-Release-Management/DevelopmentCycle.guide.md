## {{page-title}}

### Overview
The UK Core development is driven by requests for change which can come from many sources. The Change control section gives details about how this is managed.
  
### Development Cycle
The development cycle is feed from three main sources:
<ol>
<li>The Clinical and Technical Assurance Process</li>
<li>Issues raised by the FHIR Community in Simplifier</li>
<li>Issues raised from HL7 UK Ballots</li>
</ol>

See the {{pagelink:ChangeControl}} page for full details on the change control process.

### Asset Types
The first part of the development cycle is to identify the type of FHIR asset(s) and any dependencies, for example if the change is to create a new profile then there will be a need to identify any related resources required such as extensions, examples, ValueSets guide pages etc. This is required to size of the development so that resources and timescales can be planned. The required changes are then added to a JIRA backlog which is used by the UK Core Development Team to schedule the development work. 

### Adding to a Implementation Guide

The changes will be added to either:
- The UK Core FHIR Assets in development Implementation Guide
- A UK Core C&TA Release 
- A scheduled UK Core Release

Which Implementation Guide the changes appear in depends on many factors for example:
- Which release the issue was raised against
- Which process the issue was raised in (C&TA, HL7 UK Ballot etc)
- The use case that is driving the development

The {{pagelink:SimplifierPlatformStructure}} page gives further information about Implementation Guide types.

### Internal Review
Once the change has been done the UK Core Development Team will carry out an internal review and rework as necessary until the development is of the quality required. The page on {{pagelink:FHIRAssetDesign}} gives more information on the principles and design of FHIR assets which are used during internal review. 

### External Review
There is no external review until the changes are included in a release as part of the C&TA or the Ballot process but as all development is done in the public domain and therefore feedback on any change is always possible via Simplifier.  

---



