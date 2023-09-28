## `asserter`

A reference to the source of the information about the allergy. The resource being referenced SHOULD conform to one of the following:

- {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}
- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}
- <a href="https://hl7.org/fhir/R4/RelatedPerson.html">RelatedPerson Resource</a>

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

Where a human asserter is not captured or cannot be confirmed, i.e. a `Practitioner`, `Patient` or `RelatedPerson`, the provider systems SHOULD reference an `PractitionerRole.organisation` and/or `PractitionerRole.healthcareService` within a `PractitionerRole`, using the associated ODS code.

For example, asserted by "MILTON KEYNES UNIVERSITY HOSPITAL NHS FOUNDATION TRUST".

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


