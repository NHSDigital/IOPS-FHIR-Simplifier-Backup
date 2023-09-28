## {{page-title}}

Any coding / CodeableConcept element within the profile or within an extension within the profile, that is bound to a UKCore ValueSet, SHALL be added to the Bindings (differential) page and table, via a listing of the element in which it is to be used, the binding strength and a link to the ValueSet page within the IG. 

~~~~html
## Bindings (differential)

More information about the bindings to UK Core ValueSets can be found below.

<table class="assets" title="Bindings list">
<tr>
<th class="width30">Context</th>
<th class="width20">Strength</th>
<th class="width50">Link</th>
</tr>
<tr>
<td>[context of use]</td>
<td>[strength]</td>
<td>{ {pagelink:ValueSet-UKCore-[ValueSet]}}</td>
</tr>
</table>

---
~~~~

---