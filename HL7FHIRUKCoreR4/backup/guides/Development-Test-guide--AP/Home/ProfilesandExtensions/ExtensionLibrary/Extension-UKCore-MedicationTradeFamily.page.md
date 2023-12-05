---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationTradeFamily
---
## StructureDefinition Extension-UKCore-MedicationTradeFamily

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreMedicationTradeFamily'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Medication,text:Medication}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Medication Trade family</b>- An example to illustrate the use of a trade family or brand.<br>
  {{pagelink:Example-UKCore-Extension-MedicationTradeFamily}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-MedicationTradeFamily/~issues?level=File">Report Issue for Extension-UKCore-MedicationTradeFamily</a>.
</div>


<h3 id="guidance-medicationtradefamily">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-MedicationTradeFamily}}.

---