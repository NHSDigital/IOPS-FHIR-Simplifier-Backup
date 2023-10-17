## `note`

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
<td class="width60">Information about the dispense</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">Extra information about the dispense that could not be conveyed in the other attributes.</td>
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


Not required as part of a minimum viable content; however, if this field is populated, the receiving system SHALL consume the information in the event that it contains important information (and should be treat as required) <span class="mro-circle required"></span>

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>If the system offers an end-user the option to create a <code>MedicationDispense.note</code>, it is advised that the scope of the <code>MedicationDispense.note</code> should be the dispense event only.</div>

---
