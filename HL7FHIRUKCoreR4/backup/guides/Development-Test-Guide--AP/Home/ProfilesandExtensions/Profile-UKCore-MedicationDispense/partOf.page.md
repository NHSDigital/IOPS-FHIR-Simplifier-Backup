## `{{page-title}}`

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
 id,Short_Description:short,definition,comment,
 Minimum_Cardinality:min,
 Maximum_Cardinality:max,
 left join type.code,
 left join type.targetProfile,
 left join binding.strength,
 left join binding.valueSet
where id = 'MedicationDispense.partOf'
```
<table class="baseFhir" title="Element Details">
<tr>
<td class="width40"><b>Short Description</b></td>
<td class="width60">Event that dispense is part of</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">The procedure that trigger the dispense.</td>
</tr>
<tr>
<td class="width40"><b>Comment</b></td>
<td class="width60"></td>
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

The resource being referenced SHALL conform to {{pagelink:Profile-Procedure}}

---