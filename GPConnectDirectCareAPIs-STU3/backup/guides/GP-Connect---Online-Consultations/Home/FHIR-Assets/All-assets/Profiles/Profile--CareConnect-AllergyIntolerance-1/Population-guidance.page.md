## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    The requirements may change, and may not follow the guidelines in the information standards notice: <a href="https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dapb4013-medicine-and-allergy-intolerance-data-transfer">DAPB4013: Medicine and Allergy/Intolerance Data Transfer</a>
</div>

- the `extension[encounter]` element **SHOULD** contain a reference to an associated encounter
- the `extension[allergyEnd]` element **MUST** contain the date the allergy or intolerance was recorded as resolved, if the `clinicalStatus` is set to `resolved`
- the `extension[allergyEnd].endReason` element **MUST** contain the reason why the allergy or intolerance has been resolved. In exceptional cases where for legacy data there is no `endReason` recorder in the system then this **MUST** be populated with the text "No information available"
- the `clinicalStatus` element **MUST** be populated with `active` for all active allergies, or `resolved` for resolved allergies
- the `verificationStatus` element **MUST** contain a fixed value of `unconfirmed`
- the `type` element **SHOULD** be set to `allergy` for reactions which are allergenic in nature (immunological), a value of intolerance **MAY** be used to indicate adverse reactions (not immunologic in nature). Where the type is unknown the type element may be omitted
- the `category` element **MUST** use medication for all drug allergy types, environment for all non-drug allergies. The other values in the ValueSet (food and biologic) **MUST NOT** be used
- the `criticality` element **SHOULD** used to distinguish between life-threatening (high) and non-life-threatening (low) potential as well as unable-to-assess. It **MAY** be used in addition to severity within the reaction element to express severity - for example, systems that support a severity of life-threatening **MAY** set criticality to high
- the `code` element **MUST** contain the causative agent such as food, drug or substances that has caused or may cause an allergy, intolerance or adverse reaction in this patient
- the `patient` element **MUST** contain a reference to the `Patient` who has, or had, the allergy or intolerance specified
- the `onset.DateTime` element **SHOULD** contain a date when allergy/intolerance first manifested. Currently restricted to values of `dateTime` for GP Connect
- the `assertedDate` element **MUST** contain a the datetime the record was believed to be true
- the `recorder` element **MUST** contain a reference to who recorded the allergy
- the `asserter` element **SHOULD** contain a reference to the source of the information about the allergy
- the `lastOccurrence` element **SHOULD** contain the date and/or time of the last known occurrence of a reaction event
- the `note` element **SHOULD** contain all text associated with the AllergyIntolerance including user-entered notes and qualifiers is grouped together and expressed in this field, which ensures unmapped coded values or qualifiers are not lost. **MUST** be used to contain any textual data relevant to the allergy
- the `reaction.manifestation` element **SHOULD** contain the reaction resulting from the allergy/intolerance as a code
- the `reaction.description` element **SHOULD** contain the textual description of the manifestation where no code is available
- the `reaction.severity` element **SHOULD** contain severities of `Mild`, `Moderate`, `Severe` are mapped directly to the ValueSet. Map life threatening to Severe and populate criticality with `high`
- the `reaction.exposureRoute` element **SHOULD** contain the route by which exposure to the substance causing the reaction occurred. Utilise the dm+d route codes