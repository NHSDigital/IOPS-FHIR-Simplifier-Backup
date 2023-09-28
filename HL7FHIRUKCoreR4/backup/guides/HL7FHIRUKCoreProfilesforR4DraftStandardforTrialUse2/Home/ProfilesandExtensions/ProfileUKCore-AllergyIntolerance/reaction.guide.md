## `reaction`
Details about each adverse reaction event linked to exposure to the identified substance.

The `AllergyIntolerance.reaction` is optional, but where a `severity` is available in the provider system it **MUST** be included to convey severity even if no other reaction details are explicitly available. If this is the case the `AllergyIntolerance.reaction.manifestation` **MUST** be coded as the nullFlavor `NI`.

### Element: `reaction.substance`

An optional element to record the specific substance or pharmaceutical product considered to be responsible for event.

#### Provider Systems

When recording a reaction to a medication substance, the provider system should use a dm+d concept class.

- **National Health Service dictionary of medicines and devices combination drug Virtual Therapeutic Moiety (VTM)** – just the drugs, no formulation. May be additional concepts to those in the SNOMED-CT hierarchy.
- **National Health Service dictionary of medicines and devices Virtual Medicinal Product (VMP)** - generic drug products and also generic appliance/ device concepts. May be additional concepts to those in the SNOMED-CT hierarchy and will support the recording of allergies to bandages and dressings etc. Device/appliances are concepts that would not be within scope of the SNOMED-CT pharmaceutical/biologic product hierarchy.
- **National Health Service dictionary of medicines and devices Actual Medicinal Product (AMP)** – branded drug products and branded appliance/device concepts that would not be within scope of the SNOMED-CT pharmaceutical/ biologic product hierarchy.
- **National Health Service dictionary of medicines and devices ingredient** – just the drug ingredients, no formulation. May be additional concepts to those in the SNOMED-CT hierarchy. Important to have this in addition to VTM as some things may be more specific at VTM level for example things only available as combinations where VTM would only be the combination also VTM may not identify the salt but this concept class would support that.

Alternatively, the reaction substance can be recorded using a SNOMED CT code from a union of the following.

- Substance hierarchy [105590001 | substance](https://termbrowser.nhs.uk/?perspective=full&conceptId1=105590001&edition=uk-edition) 

- Product hierarchy [373873005 | Pharmaceutical/biologic product(product)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=373873005&edition=uk-edition) 

- [196461000000101 | transfer-degraded drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196461000000101&edition=uk-edition)

- [196471000000108 | transfer-degraded non-drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196471000000108&edition=uk-edition).

#### Consumer Systems

Consumer systems may consume this data.

### Element: `reaction.manifestation` (Mandatory)

A mandatory element if a `reaction` is recorded for the clinical symptoms and/or signs that are observed or associated with the adverse reaction event.

Use nullFlavour `NI` for the case when a `reaction.severity` needs to be shared but where a `manifestation` is not known.

### Element: `reaction.description`

An optional text description about the reaction as a whole, including more verbose details of the manifestation if required.

### Element: `reaction.onset`

An optional date or date/time when the manifestation showed.

This FHIR element may be populated if known.

### Element: `reaction.severity`

An optional value from a required terminology binding containing the values;
- `mild`
- `moderate`
- `severe`

#### Provider Systems

Where a `severity` is available in the provider system it **MUST** be included to convey severity even if no other reaction details are explicitly available.

Where the severity is not known, this element should be omitted.

#### Consumer Systems

Use of this element when populated as `severe` may be used to express life threatening allergies, used in conjunction with the `AllergyIntolerance.criticality` element.

An omitted `severity` will either mean severity date is not available within the provider system or the severity is not known by the provider system.

### Element: `reaction.exposureRoute`

An optional element to identify the route by which the patient was exposed to the substance.

#### Provider Systems

If this data is available the binding should be to the [999000051000001100 | ePrescribing route of administration simple reference set](https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000051000001100&edition=uk-edition).

#### Consumer Systems

Consumer systems are recommended not to include this coded information within automated clinical decision support. This is because it could either mean two quite different things;
1. The reaction only occurs if the substance enters the body via the specified route, implying the use of other routes is safe.

OR


2. The reaction was identified when the substance entered the body via the specified route, but could also react when using other routes.

### Element: `reaction.note`

An optional element for when the clinical user wishes to provides supporting textual information for the reaction that cannot be conveyed within other elements of the backbone element.

See the related guidance above for `AllergyIntolerance.note`.

---
