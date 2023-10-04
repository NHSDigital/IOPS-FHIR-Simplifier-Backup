## StructureDefinition Extension-UKCore-AdditionalContact

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAdditionalContact'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-ServiceRequest,text:ServiceRequest}}</td>
</tr>
</table>

</div>
<br>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')"><i class="fa fa-folder-tree"></i> Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')"><i class="fa fa-table-list"></i> Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')"><i class="fa fa-code"></i> XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')"><i class="fa fa-brackets-curly"></i> JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')"><i class="fa fa-file-pen"></i> Examples</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  <h3>Tree View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact, buttons, expand}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Additional Contact</b> - An example to illustrate providing an additional contact with a service request.<br>
{{pagelink:Example-UKCore-ServiceRequest-Extension-AdditionalContact}}
<br><br>
</div>

### Guidance
The resource being referenced SHALL conform to one of the following:

- {{pagelink:Profile-Organization}}
- {{pagelink:Profile-Practitioner}}
- {{pagelink:Profile-PractitionerRole}}


---
