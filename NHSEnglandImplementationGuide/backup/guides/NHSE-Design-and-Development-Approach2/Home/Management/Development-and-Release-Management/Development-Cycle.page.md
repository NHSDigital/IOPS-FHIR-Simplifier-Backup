## {{page-title}}

### Overview
The NHSE IG development is driven by requests for change which can come from many sources. The Change control section gives details about how this is managed.
  
{{render:NHSEAssetCreation}} 

### Development Cycle
The development cycle is fed from two main sources:
<ol>
<li>The Clinical and Technical Assurance Process</li>
<li>Issues raised by the stakeholders in Simplifier</li>
</ol>

See the {{pagelink:Change-Control}} page for full details on the change control process.

### Asset Types
The first part of the development cycle is to identify the type of FHIR asset(s) and any dependencies, for example if the change is to create a new profile then there will be a need to identify any related resources required such as extensions, examples, ValueSets guide pages etc. This is required to size of the development so that resources and timescales can be planned. The required changes are then added to a JIRA backlog which is used by the IOPS Team to schedule the development work. 

### Release Following Changes
Releases timings of the NHS England IG and FHIR assets will be decided by IOPS and the team will decide on the actual scheduling based of a number of factors for example:
- Available resource
- Program delivery time scales

### Internal Review
Once the change has been done the IOPS will carry out an internal review and rework as necessary until the development is of the quality required. The page on [Asset Design](https://simplifier.net/guide/NHSE-Design-and-Development-Approach2/Home/Asset-Design?version=current "Title"). gives more information on the principles and design of FHIR assets which are used during internal review. 

### External Review
There is no external review until the changes are included in a pre-release as part of the C&TA but as all development is done in the public domain and feedback on any change is always possible via Simplifier.  

---



