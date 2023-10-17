## `statusReason[x]`

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
<td class="width60">Why a dispense was not performed</td>
</tr>
<tr>
<td class="width40"><b>Definition</b></td>
<td class="width60">Indicates the reason why a dispense was not performed.</td>
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
<td class="width40"><b>Data Type</b></td>
<td class="width60">CodeableConcept: http://hl7.org/fhir/ValueSet/medicationdispense-status-reason (example)<hr class="nomargin">Reference: http://hl7.org/fhir/StructureDefinition/DetectedIssue
</td>
</tr>
</tr>
</table>

</div>
</div>

A coded reason for why a dispense was not performed.

This elementSHOULD only be populated when the `MedicationDispense.status` is either `cancelled`, `stopped` or `declined`.

---