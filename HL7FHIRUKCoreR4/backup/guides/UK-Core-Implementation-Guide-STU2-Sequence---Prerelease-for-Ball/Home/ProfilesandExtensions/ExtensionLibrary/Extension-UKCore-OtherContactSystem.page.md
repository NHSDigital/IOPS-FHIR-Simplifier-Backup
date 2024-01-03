## StructureDefinition Extension-UKCore-OtherContactSystem

<!--Information about other contact methods which could be used in addition to those listed in `ContactPoint.system` and `RelatedPerson.telecom.system`.

### Purpose
This extension extends the ContactPoint datatype to support the exchange of other contact system information, which is currently not supported by the FHIR standard.
-->

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreOtherContactSystem'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>ContactPoint.system</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-OtherContactSystem}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Other Contact System</b> - An example to illustrate other contact methods for a patient. </br>
{{pagelink:Example-UKCore-Patient-Extension-OtherContactSystem}}
<br><br>
</div>

### Guidance
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-OtherContactSystem}}.

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The datatype of this extension was changed from <code>valueCoding</code> in UK Core STU1 Sequence, to <code>valueCodeableConcept</code> in this release, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div> 

---
