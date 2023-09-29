## Background

### Medication orders within UK ePMA systems and how the are supported with FHIR

Typically within UK hospitals, ePMA systems support three types of medication request (or order).

1. Initial medication request
2. Re-supply of a previous medication
3. Discharge medication request

#### Initial medication request

Represents the first time a request for a medicine is made for a patient. This can include a long-term medicine or an acute medicine for a specified duration. Each request shall be for one medication.

The structured dosage instruction shall specify the administration requirement, for example: "50 mg daily with food", and any time or dosing bounds - for example: "for 7 days", all represented in the structured and machine readable [FHIR dosage structure](http://hl7.org/fhir/stu3/dosage.html#Dosage).

Most ePMA medication requests are deemed to be on-going unless specifically stated within the dosage instruction with date, time or dose bounds. Where no end criteria is specified the hospital pharmacy will typically dispense a quantity of medication as per their local agreed best practice. For example, sufficient medication for a given number of days, depending on how frequently the ward and pharmacy want to re-order medication. 

When more medication is required, a “Re-Supply Medication Request” should be submitted.

#### Re-Supply Medication Request

When a patient requires a re-supply of the same medication as previously ordered.

For a minimum viable product (MVP) implementation it is recommended to reference a previous `MedicationRequest` using the `priorPrescription` element. This can either reference the last MedicationRequest or the first MedicationRequest. This choice can be a local implementation decision. 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The FHIR standard also allows a previous supply to be reference using the <code>basedOn</code> element. For this guidance it is recommended <code>basedOn</code>, if used, it used to reference a <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-CarePlan-1">CarePlan</a> resource.
</div>

It is recommended that a re-supply should;

- only be made against a previous order that has a **status** of `active` or `complete`
- be identical to the previous supply with regard to the **medication** and **dosageInstruction**
- allow a different **requester** and / or **recorder** to the previous supply
- allow a different **dispenseRequest** (if implemented within the system) to the previous supply to cater for the scenario where a re-supply is required for a certain number of days or quantity of medication. For example, a final supply prior to the end of the treatment or course or before the patient is to be discharged.


#### Discharge Medication Request

When a patient requires medication that they will take away with them on discharge from hospital for administration at home. This could be following an inpatient stay or from an outpatient department.

A discharge medication request is identified using the **category** element with a value of `discharge`.

Discharge medication for patient self-administration at home may be;

- labelled differently to medications administered within the hospital
- include specific dispensing instructions for pharmacy within the **dispenseRequest** element
- identified differently within the ePMA system to ensure the patient receives the medication before they leave the hospital
- used as in input for discharge instructions for the patient’s GP for medication that should be continued.

---
