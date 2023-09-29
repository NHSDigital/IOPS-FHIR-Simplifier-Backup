# {{page-title}}

The reader must be familiar with the [NHS Dictionary of Medicines and Devices](https://apps.nhsbsa.nhs.uk/DMDBrowser/DMDBrowser.do) (dm+d) and [SNOMED-CT](https://termbrowser.nhs.uk/). The dm+d is the NHS choice for recording details of medicines and devices in the electronic patient record and is the medicines standard approved by the Standardisation Committee for Care Information (SCCI) as an NHS Fundamental standard. 

All dm+d concepts are included in the SNOMED-CT UK Drug Extension and all dm+d codes are SNOMED-CT codes. The basic dm+d structure with the associated SNOMED CT UK drug extension Trade Family concept class is shown below, with examples at each level.

{{render: dm-d-concepts-v2}}{: .img-responsive }

<br />

## Product-based vs Dose-based Prescribing

The reader must be familiar with how prescribing processes are sometimes different between primary and secondary care settings and should read the [detailed dm+d implementation guidance](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) for each care setting published on the NHSBSA website.

All prescribing in primary care, the majority of which is performed within general practice, is using product-based prescriptions. The prescriber chooses a product, which in the dm+d model would be a `Virtual Medicinal Product` (VMP) or if a specific branded product is required, an `Actual Medicinal Product` (AMP). A VMP is a pre-coordinated SNOMED concept that defines the medication, strength, form, and possibly unit of presentation. An AMP additionally defines the supplier and a brand name where applicable.

Primary care prescribing uses VMP and AMP concepts because dispensing is performed, in the majority of cases, in community pharmacies for self-administration by the patient. It would not be efficient or appropriate for a pharmacist to discuss with the patient specifics of which drug dose form they would prefer. Primary care therefore deals with products where a prescription comprises of a VMP or AMP, a quantity of that product, and a dosage instruction.

Secondary care prescribing prefers to use the less specific `Virtual Therapeutic Moiety` (VTM) concept plus a dosage instruction, creating a dose-based prescription (more commonly known as an 'order' in secondary care). The combination of a VTM plus a dosage instruction gives ward clinicians the flexibility to use different formulations of medicine depending on the needs of the patient. For example, if the patient is having difficulty swallowing then the medication in a liquid form may be easier to take than a tablet form. The prescription order is typically as generic as is safely possible. In some cases it may just be a VTM plus a dose quantity, route and frequency, e.g. "Ibuprofen 400mg, oral, three times daily".

<br />

{{render: dose-vs-product-v2}}{: .img-responsive }

<br />

Both care settings would benefit from having a structured way to record dosage instructions, but it becomes essential when medicines information is shared between care settings to reduce the need for human intervention and improve patient safety. Examples of this are the identification of current medication on hospital admission or to share changes in on-going medication back to the patient's GP following hospital discharge.

Today, without an implemented dose structure, clinicians in both care settings need to convert between product-based and dose-based instructions. The few occasions when human error occurs during this conversion process can lead to significant patient harm. It is here that clinical software systems which understand structured dosage instructions can support the clinician. A dose-based instruction can be mapped to VMPs or AMPs for pharmacy stock picking lists or repeat prescribing by general practice. A product-based repeat prescription can be converted into a dose-based instruction for continued medicines administration while the patient is in hospital care.

Additionally, the growing demand for patient-facing applications to support medicines compliance can benefit from having structured dosage instructions as these can be used to trigger alerts and notifications to patients when it is time to take or reorder medication. It would also be possible for devices and machines that perform medicines administration, e.g. hospital infusion machines, to be automatically set-up to deliver the rate of medicine required or alert the clinician if incorrectly user-programmed (i.e. too fast or too slow).

## NHS dm+d concepts and impact on use of the Dosage element 

All references to medication must use the NHS standard of dm+d. The dm+d concept class used will give different levels of specificity, as required by the prescriber. 

The most generic medication instruction would specify a dm+d `Virtual Therapeutic Moiety` (VTM) plus a `Dosage` instruction. 

The most specific medication instruction, for the purposes of prescribing, would specify a dm+d `Actual Medicinal Product` (AMP) plus a `Dosage` instruction.

{{render: nhs-dmd-concepts-related-data}}{: .img-responsive }

### Virtual Therapeutic Moiety (VTM)

The most generic representation of a medication that only conveys the medication, e.g. `Paracetamol`.

The Dosage would typically express the dose as a weight or volume of medication, plus all other instructions required by the prescriber.

For example;

`Paracetamol - 500 milligrams - twice a day - for 7 days`

instead of

`Paracetamol - 1 tablet - twice a day - for 7 days` 

as when using a VTM the strength of a tablet would not be known. The typical strength of a Paracetamol tablet would be either 500 milligrams or 1 gram.

### Virtual Therapeutic Moiety (VTM) + Form

The prescriber may give a specific instruction for the form of the medication, e.g. `suppository`, within the `Medication.form` element.

The Dosage would typically express the dose as a weight or volume of medication, plus the form and other instructions required by the prescriber.

**Note:** The FHIR Medication resource can only include a single form as a CodeableConcept element. The Dosage structure does not contain an coded element that can convey a form.

For example;

`Paracetamol - suppository - 500 milligrams - twice a day - for 7 days`

### Virtual Therapeutic Moiety (VTM) + Trade Family

The UK Core profiled <code>Medication</code> resource includes an extension for <code>Extension-UKCore-MedicationTradeFamily</code> to convey a Trade Family concept.

For example;

`Paracetamol (PANADOL) - 500 milligrams - twice a day`

### Virtual Medicinal Product (VMP)

A VMP comprises of a medication + strength + form. 

The Dosage would typically express the dose using the dm+d unit form dose unit of measure, plus all other instructions required by the prescriber.

For example;

`Paracetamol 500mg tablets - 1 tablet - twice a day - for 7 days`

instead of

`Paracetamol 500mg tablets - 500 milligrams - twice a day - for 7 days`

### Virtual Medicinal Product (VMP) + Qty/UoM

A VMP plus a `MedicationRequest.dispenseRequest` would be typical for primary care prescription instructions as used by the English Electronic Prescription Service.

The Dosage would typically express the dose using the dm+d unit form dose unit of measure, the requested quantity, plus all other instructions required by the prescriber.

For example;

`Paracetamol 500mg tablets - 1 tablet - twice a day - for 7 days - 14 tablets`

### Actual Medicinal Product (AMP)

An AMP comprises of a medication + strength + form + manufacturer.

The Dosage would be as per the VMP.

For example;

`Paracetamol 500mg tablets (DE Pharmaceuticals) - 1 tablet - twice a day - for 7 days`

### Actual Medicinal Product (AMP) + Qty/UoM

The Dosage would be as per the VMP + Qty/UoM.

For example;

`Paracetamol 500mg tablets (DE Pharmaceuticals) - 1 tablet - twice a day - for 7 days - 14 tablets`

---
