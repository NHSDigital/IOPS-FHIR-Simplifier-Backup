## StructureDefinition Extension-UKCore-VaccinationProcedure

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreVaccinationProcedure'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Immunization,text:Immunization}}</td>
</tr>
</table>

</div>
<br>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  <h3>Tree View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-VaccinationProcedure}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Vaccination Procedure</b>- An example to illustrate the extension for a vaccination procedure.<br>
   {{pagelink:Example-UKCore-Immunization-Extension-VaccinationProcedure}}
   <br><br>
   <b>Covid Vaccination Procedure<br>- An example to illustrate the extension for a vaccination procedure for COVID.<br>
   {{pagelink:Example-UKCore-Immunization-Extension-VaccinationProcedure-Covid}}
   <br><br>
</div>

### Guidance
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-info-circle"></i>
Whilst there is a binding within this extension to a {{pagelink:ValueSet-UKCore-VaccinationProcedure}}
, an additional {{pagelink:ValueSet-UKCore-VaccinationProcedureSupplementary}} is available that essentially extends the UKCore-VaccinationProcedure ValueSet with SNOMED CT concepts that some systems may have used in the past on record entries that may also be relevant to the population of the UKCore-VaccinationProcedure extension within Immunization profile instances.
</div>

---
