## `dosageInstruction`

<div id="elementdetails" markdown="span" class="alert alert-baseFhir" role="alert">
<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationDispense'
select name,
join for snapshot.element 
select
 id,short,definition,comment,
 Minimum_Cardinality:min,
 Maximum_Cardinality:max
where id = 'MedicationDispense.partOf'
```
<table class="baseFhir" title="Element Details">
<tr>
<td class="width40"><b>Short Description</b></td>
<td class="width60">How the medication is to be used by the patient or administered by the caregiver</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">Indicates how the medication is to be used by the patient.</td>
</tr>
<tr>
<td class="width40"><b>Comment</b></td>
<td class="width60">When the dose or rate is intended to change over the entire administration period (e.g. Tapering dose prescriptions), multiple instances of dosage instructions will need to be supplied to convey the different doses/rates. The pharmacist reviews the medication order prior to dispense and updates the dosageInstruction based on the actual product being dispensed.</td>
</tr>
<tr>
<td class="width40"><b>Cardinality</b></td>
<td class="width60">0..*</td>
</tr>
<tr>
<td class="width40"><b>Maximum Cardinality</b></td>
<td class="width60">*</td>
</tr>
</table>

</div>
</div>

Consider aligning to the Implementation Guide for Digital Medicines, but as a minimum, `MedicationDispense.dosageInstruction.text`.

Where a structured dosage is provided, populate `MedicationDispense.dosageInstruction.text` with a human readable dosage string that is clinically equivalent to the coded dosage instruction. This is for interoperability with consuming systems that do not yet support fully structured dosing instructions.

---