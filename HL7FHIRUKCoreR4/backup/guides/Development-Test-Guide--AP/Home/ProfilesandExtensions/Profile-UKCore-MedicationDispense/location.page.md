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
 id,short,definition,comment,
 Minimum_Cardinality:min,
 Maximum_Cardinality:max
where id = 'MedicationDispense.partOf'
```
<table class="baseFhir" title="Element Details">
<tr>
<td class="width40"><b>Short Description</b></td>
<td class="width60">Where the dispense occurred</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">The principal physical location where the dispense was performed.</td>
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


The resource being referenced SHALL conform to {{pagelink:Profile-Location}}

---

