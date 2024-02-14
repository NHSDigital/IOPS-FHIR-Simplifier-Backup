## {{page-title}}

Any coding / CodeableConcept element with a binding within the profile SHALL be rendered via FQL. Any CodeableConcept element with a binding within an extension within the profile, that is bound to a UKCore ValueSet, SHALL be added to table, via a listing of the element in which it is to be used, the binding strength and a link to the ValueSet page within the IG. 

No Extensions with bindings:

~~~~html
{ {page:Home/ProfilesandExtensions/ProfileBindingsTemplate.page.md}}

---
~~~~

Where an Extension with binding exists:

~~~~html
{ {page:Home/ProfilesandExtensions/ProfileBindingsTemplate.page.md}}

<table class="addToBindings">
<tr>
<td>MedicationStatement.extension:medicationPrescribingOrganizationType</td>
<td>extensible</td>
<td>{ {pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}</td>
</tr>
</table>

---
~~~~

---