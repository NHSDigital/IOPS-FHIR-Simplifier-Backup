## {{page-title}}
All Resources SHALL be in the XML format and stored within GitHub. Snapshots SHALL NOT be used in any assets. All Profiles and Extensions SHALL be created using Firely Forge. The setting for the snapshot component in Forge, SHALL be deselected from the Options menu.

### Properties
**Filename format**
The filename SHALL be human readable with a maximum character limit of 64 digits. The physical filename format to be used for these assets is as below, where <samp>[DescriptiveName]</samp> is in PascalCase:
- **Profile:** <samp>UKCore-[Resource(-DescriptiveName)].xml</samp> <i>where the Parentheses is for derived profiles only</i>
- **Extension:** <samp>Extension-UKCore-[DescriptiveName].xml</samp>
- **ValueSet:** <samp>ValueSet-UKCore-[DescriptiveName].xml</samp>
- **CodeSystem:** <samp>CodeSystem-UKCore-[DescriptiveName].xml</samp>
- **ConceptMap:** <samp>ConceptMap-UKCore-[DescriptiveName].xml</samp>


**url property**
The url format to be used for these assets is as below, where <samp>[DescriptiveName]</samp> is in PascalCase: 
- **Profile:** <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-[Resource(-DescriptiveName)]</code> <i>where the Parentheses is for derived profiles only</i>
- **Extension** <code>https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-[DescriptiveName]</code>
- **ValueSets:** <code>https://fhir.hl7.org.uk/ValueSet/UKCore-[DescriptiveName]</code>
- **CodeSystems:** <code>https://fhir.hl7.org.uk/CodeSystem/UKCore-[DescriptiveName]</code>
- **ConceptMaps:** <code>https://fhir.hl7.org.uk/ConceptMap/UKCore-[DescriptiveName]</code>

**Common properties**
- **id:** <i> in Train-Case, where <samp>[Resource]</samp> and <samp>[DescriptiveName]</samp> is in PascalCase</i>
  - Profile: <code>UKCore-[Resource(-DescriptiveName)</code> <i>where the Parentheses is for derived profiles only</i>
  - Other assets: <code>UKCore-[DescriptiveName]</code>
- **name:** <i>in PascalCase</i>
  - Profile: <code>UKCore[Resource(DescriptiveName)</code> in PascalCase, where the Parentheses is for derived profiles only</i>
  - Other assets: <code>UKCore[DescriptiveName]</code>
- **title:** <i>in Proper Case</i>
  - Profile: <code>UK Core [Resource( DescriptiveName)</code> <i>where the Parentheses is for derived profiles only</i>
  - Other Assets: <code>UK Core [Descriptive Name]</code>
- **status:** <code>draft</code> – <i>unless stated otherwise</i>

NOTE: The  <i><samp>[DescriptiveName]</samp></i>, and specifically the **id**, must not contains any <code>.</code> characters.

---
