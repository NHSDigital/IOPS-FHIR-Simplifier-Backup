## StructureDefinition Extension-UKCore-AdmissionMethod

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Extension underwent Clinical and Technical Assurance during Sprint 4. This is a new Extension added to UK Core and should undergo review  in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAdmissionMethod'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Encounter-79976,text:Encounter.hospitalization}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Admission Method</b>- An example to illustrate the extension for an encounter to support the method by which an individual was admitted into hospital.<br>
  {{pagelink:Example-UKCore-Encounter-Extension-AdmissionMethod}}
  <br><br>
</div>

### Guidance
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-AdmissionMethod}}.

---