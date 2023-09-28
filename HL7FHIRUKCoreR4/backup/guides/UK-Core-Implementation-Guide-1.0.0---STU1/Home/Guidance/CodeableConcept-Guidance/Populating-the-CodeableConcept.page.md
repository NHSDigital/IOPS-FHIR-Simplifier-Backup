## Populating the CodeableConcept

This section shows you how to populate each field where the code carried is a SNOMED CT code and where it’s not a SNOMED CT code. It also includes population scenarios with examples.

### Field by field population guidance

#### SNOMED CT

<table id="assets">
<tr>
<th width="45%">Element</th>
<th width="55%">Definition</th>
</tr>
<tr>
<td><code>code.coding</code></td>
<td>Populate this group if a SNOMED CT concept id is stored for the item.</td>
</tr>
<tr>
<td><code>code.coding.extension</code><br/><small><small>Where <code>extension.url</code> = http://hl7.org/fhir/StructureDefinition/coding-sctdescid</small></small></td>
<td>The SNOMED CT descriptionId recorded with the item. Only populated if a descriptionId exists.</td>
</tr>
<tr>
<td><code>code.coding.extension</code><br/><small><small>Where <code>extension.url</code> = https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay</small></small></td>
<td>The display of the description id. Only populated if a descriptionId exists and there is no need to use this extension if the text is lexically identical to the text in coding.display.</td>
</tr>
<tr>
<td><code>code.coding.system</code></td>
<td>Set to <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td><code>code.coding.code</code></td>
<td>The SNOMED CT concept id stored for the item.</td>
</tr>
<tr>
<td><code>code.coding.display</code> </td>
<td>The text of the current preferred term of the SNOMED CT concept id according to the current NHS Realm Language Reference Sets.<br>The text of the preferred term of the SNOMED CT concept id.<br>The preferred term is the description specified for the concept in the NHS realm description subset. The preferred term for a concept may change over time. The sending system <b>SHOULD</b> determine the current preferred term for the concept.</td>
</tr>
<tr>
<td><code>code.coding.userSelected</code></td>
<td>Set to <code>true</code> if a user selected the SNOMED CT Code when creating/updating this item. If this is <code>false</code> then this element <b>SHALL</b> not be populated by the supplying system. <br>For consuming systems the absence of this element therefore indicates that it is <code>false</code>.</td>
</tr>
<tr>
<td><code>code.text</code></td>
<td>The original text selected/manually entered by the user for the item. <br>If the text displayed to the user when they entered the code on the system is not lexically identical to the term of the code then the displayed text <b>SHALL</b> be populated here. <br><b>Note:</b> This occurs when either the original entry was not coded or the original coding has been lost.</td>
</tr>
</table>           

<br/>

#### Other coding

<table id="assets">
<tr>
<th width="45%">Element</th>
<th width="55%">Definition</th>
</tr>
<tr>
<td><code>code.coding</code></td>
<td>Populate this group if a clinical code other than SNOMED CT is stored for the item. If there are multiple codes (that is, the item has been translated multiple times) there is a group entry per code.</td>
</tr>
<tr>
<td><code>code.coding.extension</code><br/><small><small>Where <code>extension.url</code> = http://hl7.org/fhir/StructureDefinition/coding-sctdescid</small></small></td>
<td><b>Note:</b> Do not use here if coding is not SNOMED CT.</td>
</tr>
<tr>
<td><code>code.coding.extension</code><br/><small><small>Where <code>extension.url</code> = https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay</small></small></td>
<td><b>Note:</b> Do not use here if coding is not SNOMED CT.</td>
</tr>
<tr>
<td><code>code.coding.system</code></td>
<td>The identification of the code system that defines the meaning of the symbol in the code.</td>
</tr>
<tr>
<td><code>code.coding.code</code></td>
<td>The clinical code associated with the item.</td>
</tr>
<tr>
<td><code>code.coding.display</code></td>
<td>The longest character length variant text associated with the current preferred term for the clinical code.</td>
</tr>
<tr>
<td><code><code>code.coding.userSelected</code></td>
<td>Set to <code>true</code> if a user selected this code when creating/updating this item. If this is <code>false</code> then this element <b>SHALL</b> not be populated by the supplying system.
For consuming systems the absence of this element therefore indicates that it is <code>false</code>.</td>
</tr>
<tr>
<td><code>code.text</code></td>
<td>The original text selected/manually entered by the user for the item. <br>If the text displayed to the user when they entered the code on the system is not lexically identical to the term of the code then the displayed text <b>SHALL</b> be populated here. <br><b>Note:</b> This occurs when either the original entry was not coded or the original coding has been lost.</td>
</tr>
</table>     

---