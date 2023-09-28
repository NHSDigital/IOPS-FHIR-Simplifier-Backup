## StructureDefinition Extension-UKCore-AllergyIntoleranceEnd

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAllergyIntoleranceEnd'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-AllergyIntolerance,text:AllergyIntolerance.clinicalStatus}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Allergy Intolerance End</b>- An example to illustrate the date when the allergy or intolerance was no longer valid, and/or, the reason why the allergy or intolerance is no longer valid.<br>
  {{pagelink:Example-UKCore-AllergyIntolerance-Extension-AllergyIntolEnd}}
  <br><br>
</div>

### Guidance

An optional extension to record the date and reason when the allergy was no longer clinically `active`.<br/>
If the `AllergyIntolerance.clinicalStatus` is `active` then this extension SHALL be omitted.<br/>
If the `AllergyIntolerance.clinicalStatus` is `inactive` or `resolved` then the date and reason when the allergy was identified as no longer `active` SHOULD be populated.

---
