### dm+d

The EPS programme is dependent on a standard for exchange of information on drugs and devices between prescribers, dispensers and reimbursement agencies.

The NHS Dictionary of Medicines and Devices (dm+d, ref: http://www.dmd.nhs.uk) is the NHS standard for drug and device identification. It provides a stable, unique term (description) and identifier (code) for all drugs and devices used in the treatment of patients. It enables clinical system interoperability by ensuring safe and reliable exchange of information on drugs and devices. The dm+d uses the SNOMED coding scheme (ref: http://www.snomed.org).

#### Native dm+d

Refer to the dm+d implementation guidance documents for more information related to the use of dm+d, including that related to the use of “native” dm+d. These are available from the dm+d web site (http://www.dmd.nhs.uk).
Where a medication item is not in the dm+d, current FP10 processes must be followed and no EPS prescription message will be generated.

#### Timeliness of Local dm+d Data

The dm+d terminology is updated weekly and is available to download from the NHS TRUD Service (https://isd.hscic.gov.uk).

It is important that local systems use an up-to-date version of the dm+d to ensure that new concepts or amendments within the dictionary are available. The system supplier must ensure that the version of dm+d installed at each site is no more than 2 months older than the current version of dm+d as published on the TRUD website.

Suppliers can choose to implement dm+d directly or take a value-added terminology from a 3rd party supplier. To account for those suppliers who use a 3rd party terminology, a period of 2 months is sufficient for each supplier to process, manipulate and distribute the latest version of the dm+d.

#### Non dm+d mapped medication items

If the System uses a proprietary clinical terminology in addition to the NHS dm+d, then within medication picking lists, any items not mapped to the dm+d and hence not supported by the EPS must be indicated so that the prescriber is immediately aware that an FP10 will be required for this patient.

### Restrictions for Number and Type of Medication Item on a Single Prescription

#### MedicationRequest Number Restrictions

The electronic prescription must detail all prescribed medication items that are to be dispensed using the EPS. Unlike a paper prescription where physical paper size limitations mean that the maximum number of prescribed items is limited to the size of the FP10 stationery (typically 4 items per prescription), an electronic prescription can, in theory, contain an infinite number of medication items.

#### Medication Treatment Type Restrictions

Acute and repeat prescribing medication items **must not** be contained on the same prescription as repeat dispensing items.

A prescription may contain both acute and repeat prescribing medication items, the ‘MedicationRequest.courseOfTherapyType’ entity should be populated with code `acute` “Acute Prescribing” and populate acute items without a ‘repeatNumber’ and repeat items with a ‘repeatNumber’ as per this specification.

### Splitting Items across Electronic and FP10 Prescriptions

Not all medication can be prescribed via the EPS, for example, where a mapping from a proprietary drug database to the dm+d does not exist. In such cases the default position is to prescribe medication not prescribable via the EPS on a separate FP10, thus splitting the medication across electronic and FP10 prescriptions.

It is permissible in this scenario, at the choice of either the prescriber or patient, to prescribe all medication items on an FP10 prescription.
