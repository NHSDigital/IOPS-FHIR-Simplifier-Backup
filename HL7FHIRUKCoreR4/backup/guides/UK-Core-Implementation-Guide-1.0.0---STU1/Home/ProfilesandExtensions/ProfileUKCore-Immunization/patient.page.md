## `patient`

A reference to the patient who either received or did not receive the immunisation. The resource being referenced should conform to {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}.


<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>


<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{{table:UKCore-Immunization-Sn-PatientConformVaccination-Example}}
</div>

<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{{tree:UKCore-Immunization-Sn-PatientConformVaccination-Example}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:UKCore-Immunization-Sn-PatientConformVaccination-Example}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:UKCore-Immunization-Sn-PatientConformVaccination-Example}}
</div>



### Provider Systems

Provider systems SHALL provide a `reference` and/or `identifier` that allows the consumer system to query another API if they need to access the complete **UKCore-Patient** resource. 

### Consumer Systems

Consumer systems SHALL consume this data.

---