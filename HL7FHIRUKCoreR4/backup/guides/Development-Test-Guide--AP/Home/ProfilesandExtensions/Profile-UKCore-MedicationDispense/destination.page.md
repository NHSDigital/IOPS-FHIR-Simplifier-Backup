## `destination`

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
<td class="width60">Where the medication was sent</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">Identification of the facility/location where the medication was shipped to, as part of the dispense event.</td>
</tr>
<tr>
<td class="width40"><b>Comment</b></td>
<td class="width60"></td>
</tr>
<tr>
<td class="width40"><b>Cardinality</b></td>
<td class="width60">0..1</td>
</tr>
<tr>
<td class="width40"><b>Maximum Cardinality</b></td>
<td class="width60">1</td>
</tr>
</table>

</div>
</div>


If used, consider interpreting as the **Intended Destination** in the real world, this could change between being marked as "dispensed" and the patient receiving the medication.

For example, within an inpatient setting, the patient could have been transferred to a different ward before the dispensed medication is delivered.

The resource being referenced SHALL conform to {{pagelink:Profile-Location}}

---
