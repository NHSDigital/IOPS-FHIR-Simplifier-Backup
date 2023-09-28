## Purpose  

To standardise all pages within the FHIR NHS England Implementation Guide (IG)

---

## General Rules 

- Information SHALL be unique to NHS England IG. There SHOULD NOT be any duplication of HL7 FHIR content nor any information within the profile unless it gives context for additional NHS England IG information. 
- Information SHALL NOT contradict HL7 FHIR. 
- Conformance language SHALL be written in accordance with <a href="https://build.fhir.org/conformance-rules.html#conflang">https://build.fhir.org/conformance-rules.html#conflang</a> . 
- External links to HL7 FHIR SHALL be the same version as NHS England IG. 
- Each header SHALL be in Title case unless the header wording is an element, then is SHALL be in camelCase and as an inline code. 
- Elements and values SHALL be written as an inline code. 
- The first index title will be in the markdown form as \# Header1. 
- Each following page first title shall be in the from \## Header2. 
- Sub headers within these pages SHALL be in the form \### Header3 or \#### Header4 where needed
- Each table SHALL be in HTML code.
- All lists SHOULD be in alphabetical order. 
- Line breaks SHALL be written as \<br>. 
- The end of each page SHALL have a page break, denoted by three dashes. 
- Codenames that are not headers SHALL be written in absolute terms and as inline code, e.g. \`Patient.contact.name\` 
- FHIR assets names SHALL match the casing of their defintion on HL7 FHIR. Typically this will be written in PascalCase, such as ValueSet or CodeSystem.
- When refering to SNOMED CT, it SHALL be written in capitals.
- When refering to SNOMED CT codes, the words Concept, Description, and Id SHALL be used in Title case.
- FHIR elements SHALL be fully qualified when discussed in guidance, e.g. `Procedure.note.authorReference` rather than `note.author`

---

## Naming Conventions 

|Markdown|Usage
|-
|Title Case | Any headers that are not elements 
|\<code>camelCase\</code>, or \`camelCase\` | Any elements and it’s values 
|\<code>PascalCase\</code>, or \`PascalCase\` |Any FHIR assets 

---

## Headers 

|Markdown|Usage
|-
|# [Header 1]|Any Index page title. Note: Profiles SHALL not be in inline code for the first header
|## \{ \{page-title\}\}|Any other page title
|## \`\{ \{page-title\}}\`|Any other page title which is an element 
|## [header 2] |Sub header for index page 
|### [header 3] <br> #### [header 4] | Sub headers for any pages 

---

## Hyperlinks 

|Markdown|Usage
|-
|\<a href="[link]">[link title]\</a> |External Links. Only to be used to link to pages within https://hl7.org/fhir/ and https://simplifier.net/ 
|\{ \{pagelink:[Topic url]\}\}|Internal Link. For referencing within the IG.  

**Note:** the Topic url can be found using the dropdown button within the IG editor, or for pages named 'Index' these are manually created and can be found at the top of the page. See Topic for more details.

---

## Information Boxes 

There are two information boxes in use in the IG, a blue box and a yellow box. 

Blue should be used for additional callouts of information, e.g.:
~~~~html
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <code>England-Patient</code> was added after specific review and feedback from the Digital and Interoperable Medicines Programme. It was not added under a Clinical & Technical Assurance sprint
</div>
~~~~
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <code>England-Patient</code> was added after specific review and feedback from the Digital and Interoperable Medicines Programme. It was not added under a Clinical & Technical Assurance sprint
</div>

Yellow should be used for important information, e.g.:
~~~~html
<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Where the prescription is available, it is recommended to reference via a URL - using the <code>Patient.managingOrganization.identifier</code> element rather than adding the <code>Patient</code> as a bundle - to avoid duplication.
</div>
~~~~
<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Where the prescription is available, it is recommended to reference via a URL - using the <code>Patient.managingOrganization.identifier</code> element rather than adding the <code>Patient</code> as a bundle - to avoid duplication.
</div>

---

## Balloted Information

Where guidance has been added or changed between ballots, it SHALL be highlighted in green.

For tr, td, li elements, this is done by adding <code>class="balloted"</code>

For Extensions, Profiles, ValueSets, CodeSystems that have been ADDED, this is done by adding this to the top of the relevant page - this will turn the whole of that Extension, ValueSet, CodeSystem green, or if added to a Profile page, the whole page green.

~~~~html
<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This [Asset Type] underwent Clinical and Technical Assurance during Sprint X. This is a new [Asset Type] added to NHS England IG, and should undergo review under Ballot Y.
</div>
~~~~

The same div, without the <code>id="newAsset"</code> can be used on a page to add a green banner to the page. This should be used on any guidance page that is not an asset, e.g. within CodeableConcept guidance.

<div markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This [Asset Type] underwent Clinical and Technical Assurance during Sprint X. This is a new [Asset Type] added to NHS England IG, and should undergo review under Ballot Y.
</div>

---

## Rendering Additional Content

Where guidance has been added in another IG, such as the glossary, this can be rendered in an IG using the Simpifier { {render: command }}, which can work across projects and organisations.


<div markdown="span" class="alert alert-warning" role="alert">
<h4><i class="fa fa-info-circle"></i> Important</h4>
Currently, Simplifier commands, such as FQL or pagelink / tree / xml / json / render, will not be processed by the rendered page.
</div>

<hr class="thickline">

