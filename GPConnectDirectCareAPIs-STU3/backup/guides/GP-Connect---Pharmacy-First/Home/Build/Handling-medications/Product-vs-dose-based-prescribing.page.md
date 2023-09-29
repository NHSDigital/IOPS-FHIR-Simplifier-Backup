## {{page-title}}

You must be familiar with how prescribing processes are sometimes different between primary and secondary care settings and should read the [detailed dm+d implementation guidance](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) for each care setting published on the NHSBSA website.

All prescribing in primary care, the majority of which is performed within general practice, is using product-based prescriptions. The prescriber chooses a product, which in the dm+d model would be a Virtual Medicinal Product (VMP) or if a specific branded product is required, an Actual Medicinal Product (AMP). A VMP is a pre-coordinated SNOMED concept that defines the medication, strength, form, and possibly unit of presentation. An AMP additionally defines the supplier and a brand name where applicable.

Primary care prescribing uses VMP and AMP concepts because dispensing is performed, in the majority of cases, in community pharmacies for self-administration by the patient. It would not be efficient or appropriate for a pharmacist to discuss with the patient specifics of which drug dose form they would prefer. 

Primary care therefore deals with products where a prescription comprises of a VMP or AMP, a quantity of that product, and a dosage instruction.

Secondary care prescribing prefers to use the less specific Virtual Therapeutic Moiety (VTM) concept plus a dosage instruction, creating a dose-based prescription (more commonly known as an 'order' in secondary care). The combination of a VTM plus a dosage instruction gives ward clinicians the flexibility to use different formulations of medicine depending on the needs of the patient. For example, if the patient is having difficulty swallowing then the medication in a liquid form may be easier to take than a tablet form. The prescription order is typically as generic as is safely possible. In some cases, it may just be a VTM plus a dose quantity, route and frequency - for example, 'Ibuprofen 400mg, oral, three times daily'.

<br />

{{render: dose-vs-product-v2}}

<br />

Both care settings would benefit from having a structured way to record dosage instructions, but it becomes essential when medicines information is shared between care settings to reduce the need for human intervention and improve patient safety. Examples of this are the identification of current medication on hospital admission or to share changes in on-going medication back to the patient's GP following hospital discharge.

Today, without an implemented dose structure, clinicians in both care settings need to convert between product-based and dose-based instructions. The few occasions when human error occurs during this conversion process can lead to significant patient harm. It is here that clinical software systems which understand structured dosage instructions can support the clinician. A dose-based instruction can be mapped to VMPs or AMPs for pharmacy stock picking lists or repeat prescribing by general practice. A product-based repeat prescription can be converted into a dose-based instruction for continued medicines administration while the patient is in hospital care.

Additionally, the growing demand for patient-facing applications to support medicines compliance can benefit from having structured dosage instructions as these can be used to trigger alerts and notifications to patients when it is time to take or reorder medication. It would also be possible for devices and machines that perform medicines administration, for example, hospital infusion machines, to be automatically set up to deliver the rate of medicine required or alert the clinician if incorrectly user-programmed (for example, too fast or too slow).

---