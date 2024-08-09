## {{page-title}}

The list below contains the element differences between the UKCore and HL7. 

{{page:Home/Design/Metadata-Design/Base-Resource-Metadata.page.md}}

### StructureDefinition Content

View further information about <a href="https://www.hl7.org/fhir/R4/structuredefinition.html" Target="_blank">FHIR Resource StructureDefinition - Content</a>.

{{page:Home/Design/Metadata-Design/Common-MetaData.page.md}}
    <tr>
        <td>fhirVersion</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>The version of the FHIR specification on which this StructureDefinition is based - this is the formal version of the specification, without the revision number, e.g. <i>[publication].[major].[minor]</i>.<br><br>The UKCore mandates the use of this element.</td>
    </tr> 
<tr>
        <td>purpose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>This provides traceability of ''why'' the resource is either needed or ''why'' it is defined as it is. This SHOULD contain the correct usage of the profile, for instance when it is similar to another profile examples of the expected use cases and examples which would be a misuse of the profile. The purpose is not to record the scope if these are subject to change, these SHALL be entered into the IG 'example use cases' section instead. </td>
</tr>
<tr>
        <td>baseDefinition</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>canonical(StructureDefinition)</td>
        <td>The baseDefinition SHALL be a complete URI referencing the relevant HL7 FHIR resource for UK Core base profiles, and the relevant UK Core base profile for any UK Core derived profiles. </td>
    </tr>
    <tr>
        <td>snapshot</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>BackboneElement</td>
        <td>Snapshots SHALL be present within the UK Core package and only rendered when creation of the package. Snapshots SHALL NOT be present within the UKCore GitHub Repo.</td>
    </tr>
    <tr>
        <td>differential<br>.element</td>
        <td>1..*</td>
        <td>1..*</td>
        <td>ElementDefinition</td>
        <td>When used for extensions, the element ID SHALL be <code><i>[Profile]</i>.extension:<i>[Extension name without the ExtensionUKCore prefix, in camelCase]</i></code>. E.g, for ExtensionUKCoreBirthSex this will be <code>Patient.extension:birthSex</code>  </td>
  </tr>
  <tr>
        <td>differential<br>.element<br>.sliceName</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>string</td>
        <td>When used for extensions, the element ID SHALL be <code><i>[Extension name without the ExtensionUKCore prefix, in camelCase]</i></code>. E.g, for ExtensionUKCoreBirthSex this will be <code>birthSex</code> </td>
  </tr>
  <tr>
        <td>differential<br>.element<br>.defaultValue[x]</td>
        <td>0..1</td>
        <td>0..0</td>
        <td>*</td>
        <td>Defining default values creates many difficulties in implementation (e.g. when is a value missing?). For these reasons, default values SHALL NOT be used within the UKCore.</td>
  </tr>
</table>

---
