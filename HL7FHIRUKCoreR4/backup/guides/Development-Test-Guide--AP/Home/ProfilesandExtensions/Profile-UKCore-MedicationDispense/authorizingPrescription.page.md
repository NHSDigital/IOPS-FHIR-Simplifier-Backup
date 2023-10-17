## `authorizingPrescription`

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
<td class="width60">	Medication order that authorizes the dispense</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">Indicates the medication order that is being dispensed against.</td>
</tr>
<tr>
<td class="width40"><b>Comment</b></td>
<td class="width60">Maps to basedOn in Event logical model.</td>
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


This is a required element where the prescription is known and available when constructing the `MedicationDispense` resource.

**Supply Events**

Examples of where medications can be supplied without a prescription are shown below:

- Emergency supply
- Over The Counter (OTC)
- Patient Group Directions (PGD) 
- Minor Ailment Schemes.

**Dispense Events**

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Where the prescription is available, it is recommended to reference via a URL - using the <code>MedicationDispense.authorizingPrescription.identifier</code> element rather than adding the <code>MedicationRequest</code> as a bundle - to avoid duplication.
</div>

The resource being referenced SHALL conform to {{pagelink:Profile-MedicationRequest}}

---
