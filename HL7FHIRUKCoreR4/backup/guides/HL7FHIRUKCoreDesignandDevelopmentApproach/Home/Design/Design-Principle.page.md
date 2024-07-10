---
topic: FHIRAssetDesign
---

# FHIR Assets

This section documents the approach used by the UK Core Development team to produce and maintain the UK Core Implementation Guides and the UK Core FHIR assets. It will be updated and matured in line with decisions taken during the Clinical and Technical Assurance process. This documentation is aimed at the technical reader and is included as reference material. The approach is based on the design principles.

## Conformance

The UK Core conforms to the HL7 FHIR® specification (Release 4) and its assets are profiles of the corresponding base HL7 FHIR resources.

Further information about <a href="https://hl7.org/fhir/conformance-module.html">conformance</a> in FHIR is available. 


---

# Design Principle

## Key Principle:
<blockquote>FHIR assets must not be England specific and must be capable of representing the requirements of each UK nation identified during collaboration.</blockquote>

## Other Principles

### Reference DataType

If there is a draft or active UKCore version of a Resource then this Profile SHALL be used as the reference. If there is no UKCore version available then the reference SHALL be the HL7 Resource version.

### FHIR Resource Spelling

FHIR Resources, along with ValueSets, CodeSystems and ConceptMaps use the American-English spelling, for example Organization. The UKCore approach is to use American-English for any Profile, Extension, ValueSet, CodeSystem, and ConceptMap names, and when directly referring to the names within the Implementation Guide, otherwise using the British-English for all other aspects.

### Extensions

There is a UK Core requirement to develop extensions based on any equivalent CareConnect STU3 extensions. 
The exception to this is where an extension is no longer needed because either
-  the data can be carried in a new element for a relevant resource in FHIR R4 
-  a corresponding common extension has been developed in FHIR R4  

Extension will be constrained (hard coded) into profiles to profiles after agreement during Clinical and Technical assurance.  

The Implementation Guide for the UK Core will include an Extension Library page, which will list extensions and their corresponding UK Core profiles. There is no requirement to profile HL7 extensions locally. Where a HL7 extension is identified as in scope, a link to it will be added on the Extension Library page under HL7 Common Extensions.

Read more about <a href="https://www.hl7.org/fhir/r4/extensibility.html" Target="_blank">FHIR Extensions</a> and {{pagelink:extension-design}}.   


### Cardinalities

- FHIR resource element cardinalities will only be amended, if clinical justifications are agreed during Clinical and Technical assurance.
- No elements will be removed unless deemed clinically unsafe following consultation and agreement during Clinical and Technical assurance.   

Read more about FHIR resource <a href="http://hl7.org/fhir/r4/profiling.html#cardinality" Target="_blank">cardinalities</a>.

### Slicing

- SHALL only be used where it enforces structure in a profile, for example
  -  for a ValueSet binding 
  -  for the representation of an identifier in a list, such as a patient's NHS number
- Slicing SHALL be Open e.g. one or more additional slices can be added.   

Read more about <a href="https://www.hl7.org/fhir/r4/profiling.html#slicing" Target="_blank">Slicing</a> in FHIR.

### Must Support

- Will only be used when there is a requirement arising from a use case identified during Clinical and Technical assurance.   

Read more about <a href="http://hl7.org/fhir/r4/profiling.html#mustsupport" Target="_blank">"Must Support"</a> in FHIR.

### ValueSets

#### Binding Strengths

The UKCore ValueSet binding strength SHOULD be decided as part of the Clinical and Technical Assurance, but the general philosophy is as the following:

- **required** - Used only when defined as 'required' by the FHIR standard, or when decided as part of the Clinical and Technical Assurance. 
- **extensible** - All ValueSets SHOULD be set to 'extensible', where not defined as 'required' by the FHIR standard, or 'preferred' by the UKCore standard.
- **preferred** - Used when the ValueSet contains SNOMED CT or dm+d concepts due to their inherent complexities, or when decided as part of the Clinical and Technical Assurance.
- **example** - Decided as part of the Clinical and Technical Assurance.

Read more about <a href="https://www.hl7.org/fhir/r4/terminologies.html#valuesets" Target="_blank"> ValueSets</a> and <a href="https://www.hl7.org/fhir/r4/terminologies.html#strength" Target="_blank"> ValueSet bindings</a> in FHIR.

### Validation

All FHIR assets SHALL be validated before being publicly available. See {{pagelink:Validation-of-Implementations}} for more details.

### Constraints

Constraints allow for validation against more complex calculations, giving either a warning or error if the criteria has not been met. All constraints SHALL have:

- **Key** - Unique, in the form of <samp>ukcore-<i>[asset abbreviation]-[3 digit number]</i></samp>
- **Severity** - Either <samp>error</samp> if the expression SHALL be met and rejected as a invalid resource if not, or <samp>warning</samp> if the expression SHOULD be met, but not rejected if not.
- **Human description** - A human readable description of how the expression is to be met.
- **Expression** - A FHIRPath rule that evaluates to true if run on the element. If validation returns false then it will produce an error or warning condition.

Where the severity is a <samp>warning</samp>, the Human Description will say SHOULD, where the severity is <samp>error</samp>, it will say SHALL.

Warning constraints that have been inherited within a derived profile may be inhibited using the <code>suppress</code> element only if it is deemed that the warning is incorrect for this profile.

<i>Note</i>: At this time constraints contained within derived profiles cannot be validated by the GitHub Validator, only by swagger once a package has been created containing the derived profile. Constraints can be tested beforehand using the <a href="https://simplifier.net/fhirpath?filepath=package/CapabilityStatement-base.json&scope=hl7.fhir.r4.core@4.0.1&query=">Simplifer FHIRPath Playground</a>, although caution is to be used as this only validates the FHIRPath on the StructureDefinition element.

More information can be found within the <a href="https://www.hl7.org/fhir/R4/conformance-rules.html#constraints">Conformance Rules</a> and the <a href="https://www.hl7.org/fhir/R4/elementdefinition-definitions.html#ElementDefinition.constraint">Element Definition</a>.

---


