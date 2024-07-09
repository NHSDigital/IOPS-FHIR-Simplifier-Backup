## {{page-title}}

### manifestation

`AllergyIntolerance.reaction.manifestation` is a sub-element of `AllergyIntolerance.reaction`, which is optional (0..*) - so if there is no manifestation known, then don’t send a `AllergyIntolerance.reaction` FHIR element.

Anything from the clinical finding hierarchy ( 404684003 | clinical finding (finding) | ), including the HL7 `nullFlavors` are documented below.

- The `AllergyIntolerance.reaction.manifestation` CodeableConcept ValueSet is Extensible.
- If you have a code, then goes in Manifestation CodeableConcept.
- Where no code is known (but a manifestation needs to be recorded) then populate the `AllergyIntolerance.reaction.manifestation` CodeableConcept with the value from the HL7 FHIR `NullFlavor` ValueSet of "UNC" - "un-encoded" and populate text of manifestation in `AllergyIntolerance.reaction.description`.
- When patient is asked about reaction, but doesn’t know the reaction then populate the `AllergyIntolerance.reaction.manifestation` CodeableConcept with the value from the HL7 FHIR `NullFlavor` ValueSet of "ASKU" - "asked but unknown".
- When the reaction details cannot be determined / verified, then then populate the `AllergyIntolerance.reaction.manifestation` CodeableConcept with the value from the HL7 FHIR `NullFlavor` ValueSet of "NI" - "No Information".

### substance

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: The <code>AllergyIntolerance.reaction.substance</code> element <b>SHOULD NOT</b> be populated.
</div>


### onset

This FHIR element may be populated if known.


### exposureRoute

This FHIR element may be populated with a value from dm+d routes refset. As a SNOMED Expression

`^999000051000001100 |ePrescribing route of administration simple reference set|`


### note

This FHIR element **MUST NOT** be used and the information must where available, always be carried in the `Composition.section.text` FHIR element.

---