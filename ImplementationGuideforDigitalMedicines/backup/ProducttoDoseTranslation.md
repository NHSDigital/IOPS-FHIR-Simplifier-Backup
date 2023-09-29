# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    This page is in DRAFT Experimental status.
</div>

## Overview

This page describes an important functional requirement for many system implementations using Dose Syntax. Structured Dose Syntax information must be capable of being used to support dose-based and product-based prescribing, and there is a requirement to convert between the two - e.g. to convert a product-based prescription to dose-based prescription.

Details of the requirements for dosage format conversion are highly use-case dependent and will be addressed as work in specific use-case areas develops.

### Example Use Case

A Trust ePMA clinical system consuming a product-based instruction, such as that which could come from a GP system for a patient's current medication, and convert to the most generic, but clinically safe, dose-based instruction for continued care while an in-patient.

`Paracetamol 250mg/5ml oral solution, 10 millilitre - daily`

Could be safely converted to;

`Paracetamol - 500 milligram - daily`

Allowing a ward to administer the Paracetamol in whatever form and route best that suits the needs of the patient, so could be in solid, liquid or any other medicinal form available for Paracetamol.

### High Level Process Description

A product-based `MedicationRequest` or `MedicationStatement` using a dm+d VMP or AMP can be converted into a dose-based instruction using a VTM via this process.

1. Use the dm+d data model to break the VMP or AMP into it's constituent parts.

2. Use the [dm+d Secondary Care Implementation Guidance](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) to identify which elements of a complete dosing instruction may be safely omitted.

3. Apply any relevant clinical adjustments, such as a change to `route` and/or `form`.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
Page in draft, more to follow...
</div>

### Worked Example A

The patient is admitted to an Acute Trust. Current medication is identified from the GP record, as `MedicationStatement` resources. The admissions clinician decides which medication to continue, change or stop while in care as an inpatient.

The patient has a single current medication on their GP record, which is required to be continued while an in-patient.

`Fluoxetine 10mg tablets - 1 tablet - twice a day`

```xml
<!-- NOTE - only relevant elements are includes in this example -->
<MedicationStatement>
	<medicationCodeableConcept>
		<coding>
			<system value="https://dmd.nhs.uk" />
			<code value="373965000" />
			<display value="Fluoxetine 10mg tablets" />
		</coding>
	</medicationCodeableConcept>
	<dosage>
		<timing>
			<repeat>
				<frequency value="2" />
				<period value="1" />
				<periodUnit value="d" />
			</repeat>
		</timing>
		<doseAndRate>
			<doseQuantity>
				<value value="1" />
				<unit value="tablet" />
				<system value="http://snomed.info/sct" />
				<code value="385055001" />
			</doseQuantity>
		</doseAndRate>
	</dosage>
</MedicationStatement>
```

The VMP `Fluoxetine 10mg tablets` breaks down to the following data items.

| Data Item | Value | Code |
|----|----|----|
|VTM|Fluoxetine|53640004|
|Licensed Route|oral|26643006|
|Form|tablet|385055001|
|Strength|10| |
|Strength UoM|mg|258684004|

The `medicationCodeableConcept` element is changed from using the VMP to using the VTM.

A `route` element is added.

The coded `form` is not required for a safe prescription in this type of medication. If a `form` needs to be specified then this element exists within the `Medication` resource so would need to replace the `medicationCodeableConcept` with either a referenced or contained `Medication` resource.

The `doseAndRate` element is changed from using a quantity based on the unit dose unit of measure for the VMP, to using a coded strength. The SNOMED coded `mg | 258684004` is converted to the UCUM coded `milligram | mg`. This is not strictly nessasary but where a UCUM unit of measure exists, it should be used over SNOMED.

```xml
<!-- NOTE - only relevant elements are includes in this example -->
<MedicationRequest>
	<medicationCodeableConcept>
		<coding>
			<system value="https://dmd.nhs.uk" />
			<code value="53640004" />
			<display value="Fluoxetine" />
		</coding>
	</medicationCodeableConcept>
	<dosage>
		<timing>
			<repeat>
				<frequency value="2" />
				<period value="1" />
				<periodUnit value="d" />
			</repeat>
		</timing>
		<route>
			<coding>
				<system value="http://snomed.info/sct" />
				<code value="26643006" />
				<display value="oral" />
			</coding>
		</route>
		<doseAndRate>
			<doseQuantity>
				<value value="10" />
				<unit value="milligram" />
				<system value="http://unitsofmeasure.org" />
				<code value="mg" />
			</doseQuantity>
		</doseAndRate>
	</dosage>
</MedicationRequest>
```

This medication can now be continued using any suitable oral formulation, e.g. `tablet`, `capsule`, `oral solution` or `oral suspension`.

### Worked Example B

The patient is admitted to an Acute Trust. Current medication is identified from the GP record, as `MedicationStatement` resources. The admissions clinician decides which medication to continue, change or stop while in care as an inpatient.

The patient has a single current medication on their GP record, which is required to be continued while an in-patient.

`Paracetamol 250mg/5ml oral solution, 10 millilitre - daily`

```xml
<!-- NOTE - only relevant elements are includes in this example -->
<MedicationStatement>
	<medicationCodeableConcept>
		<coding>
			<system value="https://dmd.nhs.uk" />
			<code value="13004311000001103" />
			<display value="Paracetamol 250mg/5ml oral solution" />
		</coding>
	</medicationCodeableConcept>
	<dosage>
		<timing>
			<repeat>
				<frequency value="1" />
				<period value="1" />
				<periodUnit value="d" />
			</repeat>
		</timing>
		<doseAndRate>
			<doseQuantity>
				<value value="10" />
				<unit value="millilitre" />
				<system value="http://unitsofmeasure.org" />
				<code value="ml" />
			</doseQuantity>
		</doseAndRate>
	</dosage>
</MedicationStatement>
```

The VMP `Paracetamol 250mg/5ml oral solution` breaks down to the following data items.

| Data Item | Value | Code |
|----|----|----|
|VTM|Paracetamol|90332006|
|Licensed Route|oral|26643006|
|Form|oral solution|385023001|
|Strength Numerator|50| |
|Strength UoM|mg|258684004|
|Strength Denominator|1| |
|Strength UoM|ml|258773002|

The `medicationCodeableConcept` element is changed from using the VMP to using the VTM.

A `route` element is added.

The coded `form` is not required for a safe prescription in this type of medication. If a `form` needs to be specified then this element exists within the `Medication` resource so would need to replace the `medicationCodeableConcept` with either a referenced or contained `Medication` resource.

The `doseAndRate` element is changed from using a quantity based on the unit dose unit of measure for the VMP, to using a coded strength. The calculation is `10ml/1ml x 50mg = 500mg`. The SNOMED coded `mg | 258684004` is converted to the UCUM coded `milligram | mg`. This is not strictly nessasary but where a UCUM unit of measure exists, it should be used over SNOMED.

The clinician may wish to allow alternative `route` information, for example, if the patient may have difficulties swallowing oral medication. At the time of writing, the FHIR standard only permits one coded `route`. In this example, route can be omitted and still remain a safe prescription.

```xml
<!-- NOTE - only relevant elements are includes in this example -->
<MedicationRequest>
	<medicationCodeableConcept>
		<coding>
			<system value="https://dmd.nhs.uk" />
			<code value="90332006" />
			<display value="Paracetamol" />
		</coding>
	</medicationCodeableConcept>
	<dosage>
		<timing>
			<repeat>
				<frequency value="1" />
				<period value="1" />
				<periodUnit value="d" />
			</repeat>
		</timing>
		<doseAndRate>
			<doseQuantity>
				<value value="500" />
				<unit value="milligram" />
				<system value="http://unitsofmeasure.org" />
				<code value="mg" />
			</doseQuantity>
		</doseAndRate>
	</dosage>
</MedicationRequest>
```

This medication can now be continued using any suitable formulation, for which for Paracetamol there are many available formulation and route combinations.

---
