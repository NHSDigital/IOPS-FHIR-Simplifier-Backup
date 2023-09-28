## {{page-title}}
All Resources SHALL be in the XML format and stored within GitHub. Snapshots SHALL NOT be used in any assets. All Profiles and Extensions SHALL be created using Firely Forge. The setting for the snapshot component in Forge, SHALL be deselected from the Options menu.

### Properties
**Filename format**
The filename SHALL be human readable with a maximum character limit of 64 digits. The physical filename format to be used for these assets is as below, where <samp>[Name]</samp> is in PascalCase:
- **Profile:** <samp>UKCore-[Name].xml</samp>
- **Extension:** <samp>Extension-UKCore-[Name].xml</samp>
- **ValueSet:** <samp>ValueSet-UKCore-[Name].xml</samp>
- **CodeSystem:** <samp>CodeSystem-UKCore-[Name].xml</samp>
- **ConceptMap:** <samp>ConceptMap-UKCore-[Name].xml</samp>


**url property**
The url format to be used for these assets is as below, where <samp>[Name]</samp> is in PascalCase: 
- **Profile:** <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-[Name]</code>
- **Extension** <code>https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[Name]</code>
- **ValueSets:** <code>https://fhir.hl7.org.uk/ValueSet/UKCore-[Name]</code>
- **CodeSystems:** <code>https://fhir.hl7.org.uk/CodeSystem/UKCore-[Name]</code>
- **ConceptMaps:** <code>https://fhir.hl7.org.uk/ConceptMap/UKCore-[Name]</code>

**Common properties**
- **id:** <code>UKCore-[Name]</code> - <i><samp>[Name]</samp> is in PascalCase</i>
- **name:** <code>UKCore[Name]</code> - <i><samp>[Name]</samp> is in PascalCase</i>
- **title:** <code>UK Core [Name]</code> – <i><samp>[Name]</samp> is in Proper Case</i>
- **status:** <code>draft</code> – <i>unless stated otherwise</i>

NOTE: The  <i><samp>[Name]</samp></i>, and specifically the **id**, must not contains any <code>.</code> characters.

---
