## `quantity`

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
<td class="width60">Amount dispensed</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">The amount of medication that has been dispensed. Includes unit of measure.</td>
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


This element could be useful for discharge prescriptions (TTO) when representing "1 of something", for example:

- 1 pack
- 1 tablet
- 1 bottle.

It may be simpler to _always_ express as dose units. For example;

- 14 tablets
- 50 ml.

---
