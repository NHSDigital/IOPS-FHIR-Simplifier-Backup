## StructureDefinition Extension-UKCore-Coverage

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCoverage'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-ServiceRequest-88746,text:ServiceRequest}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Coverage</b>- An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
  {{pagelink:Example-UKCore-ServiceRequest-Extension-Coverage}}
  <br><br>
</div>

### Guidance
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-FundingCategory}}.

---