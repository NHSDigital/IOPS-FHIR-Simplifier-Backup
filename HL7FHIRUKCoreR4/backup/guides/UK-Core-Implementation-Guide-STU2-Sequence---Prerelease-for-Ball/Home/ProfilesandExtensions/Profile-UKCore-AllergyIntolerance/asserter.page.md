## `asserter`

A reference to the source of the information about the allergy. 

The resource being referenced SHOULD conform to one of the following:

- {{pagelink:Profile-Patient-88961}}
- {{pagelink:Profile-Practitioner-10758}}
- {{pagelink:Profile-PractitionerRole-55046}}
- {{pagelink:Profile-RelatedPerson-51006}}

### Provider Systems

Provider systems SHOULD provide at least the following minimum data within the referenced resource. 

`Practitioner`

- identifier
- name

`PractitionerRole`

- identifier
- practitioner (as above) OR organisation.identifier OR healthcareService.identifier

`Patient`

- identifier:nhsNumber
- name

`RelatedPerson`

- identifier
- name
- patient

Where a human asserter is not captured or cannot be confirmed, i.e. the asserter is not a `Practitioner`, `Patient` or `RelatedPerson`, the provider systems SHOULD reference a `PractitionerRole.organisation` and/or `PractitionerRole.healthcareService` within a `PractitionerRole` resource, using the associated ODS code, as per the following example, asserted by "MILTON KEYNES UNIVERSITY HOSPITAL NHS FOUNDATION TRUST".

#### Example of `PractitionerRole.organisation` for ODS code usage:

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>


<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{{table:UKCore-PractitionerRole-Sn-Organization-Code-Example}}
</div>

<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{{tree:UKCore-PractitionerRole-Sn-Organization-Code-Example}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:UKCore-PractitionerRole-Sn-Organization-Code-Example}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:UKCore-PractitionerRole-Sn-Organization-Code-Example}}
</div>

---
