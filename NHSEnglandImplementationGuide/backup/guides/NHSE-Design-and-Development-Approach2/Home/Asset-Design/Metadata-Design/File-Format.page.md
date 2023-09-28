## {{page-title}}

All Resources SHALL be in the XML format and stored within GitHub. Snapshots SHALL NOT be used in any assets. All Profiles and Extensions SHALL be created using Firely Forge. The setting for the snapshot component in Forge, SHALL be deselected from the Options menu.

### Properties
**Filename format**
The filename SHALL be human readable with a maximum character limit of 64 digits. The physical filename format to be used for these assets is as below, where <samp>[Name]</samp> is in PascalCase:

- **Profile:** <samp>England-[Name].xml</samp>
- **Extension:** <samp>Extension-England-[Name].xml</samp>
- **ValueSet:** <samp>ValueSet-England-[Name].xml</samp>
- **CodeSystem:** <samp>CodeSystem-England-[Name].xml</samp>
- **NamingSystem:** <samp>NamingSystem-England-[Name].xml</samp>
- **Example:** <samp>England-[Name]-Example.xml</samp>


**url property**
The url format to be used for these assets is as below, where <samp>[Name]</samp> is in PascalCase: 
- **Profile:** <code>https://fhir.nhs.uk/StructureDefinition/England-[Name]</code>
- **Extension** <code>https://fhir.nhs.uk/StructureDefinition/Extension-England-[Name]</code>
- **ValueSet:** <code>https://fhir.nhs.uk/ValueSet/England-[Name]</code>
- **CodeSystem:** <code>https://fhir.nhs.uk/CodeSystem/England-[Name]</code>
- **NamingSystem:** <code>https://fhir.nhs.uk/Id/England-[Name]</code>


**Common properties** 

- **id:** <code>England-[Name]</code> - <samp>[Name]</samp> is in PascalCase
- **name:** <code>England[Name]</code> - <samp>[Name]</samp> is in PascalCase
- **title:** <code>England [Name]</code> – <samp>[Name]</samp> is in Proper Case
- **version:** <code>Major.Minor.Patch</code>
- **date:** <code>YYYY-MM-DD</code>
- **status:** <code>draft</code> – or active after C&TA completion

---
