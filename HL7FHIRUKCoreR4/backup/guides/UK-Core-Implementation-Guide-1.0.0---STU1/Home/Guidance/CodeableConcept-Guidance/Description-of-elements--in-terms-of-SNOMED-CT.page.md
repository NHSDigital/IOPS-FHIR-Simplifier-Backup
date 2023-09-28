## Description of elements (in terms of SNOMED CT)

<table id="assets">
<tr>
<th width="45%">Element</th>
<th width="55%">Description</th>
</tr>
<tr>
<td><code>code</code></td>
<td>The wrapper element for the CodeableConcept.</td>
</tr>

<tr>
<td><code>code.coding</code></td>
<td>The wrapper element for the coded part of the CodeableConcept.</td>
</tr>

<tr>
<td><code>code.coding.extension.url</code></td>
<td>The HL7 common extension for providing the SNOMED CT Description ID for the display.<br/><small>Value = <code>http://hl7.org/fhir/StructureDefinition/coding-sctdescid</code></small></td>
</tr>

<tr>
<td><code>code.coding.extension.valueId</code><br/><small>Where <code>extension.url</code> = http://hl7.org/fhir/StructureDefinition/coding-sctdescid</small></td>
<td>The SNOMED CT Description ID for the display.</td>
</tr>

<tr>
<td><code>code.coding.extension.url</code></td>
<td>A UKCore extension for providing the SNOMED CT description display.<br/><small>Value = <code>https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay</code></small></td>
</tr>

<tr>
<td><code>code.coding.extension.valueString</code><br/><small>Where <code>extension.url</code> = https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay</small></td>
<td>The SNOMED CT description display. </td>
</tr>

<tr>
<td><code>code.coding.system</code></td>
<td>Holds the SNOMED CT system identifier <code>http://snomed.info/sct</code> </td>
</tr>

<tr>
<td><code>code.coding.version</code></td>
<td>Not used for SNOMED CT. </td>
</tr>

<tr>
<td><code>code.coding.code</code></td>
<td>Holds the SNOMED CT concept identifier. </td>
</tr>

<tr>
<td><code>code.coding.display</code></td>
<td>Holds the SNOMED CT concept display.  </td>
</tr>

<tr>
<td><code>code.coding.userSelected</code></td>
<td>Indicates that this concept was chosen by the user.  </td>
</tr>

<tr>
<td><code>code.text</code></td>
<td>Represents the text that was originally displayed to the user when the code was recorded.</td>
</tr>
</table>


---