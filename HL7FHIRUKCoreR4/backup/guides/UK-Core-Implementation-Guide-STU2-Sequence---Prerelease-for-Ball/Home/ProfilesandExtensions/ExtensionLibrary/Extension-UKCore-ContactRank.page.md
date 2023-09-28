## StructureDefinition Extension-UKCore-ContactRank

<!--
The preferred ranking or order of contact applied to a contact on a Patient's contact list. This is independent of the relationship type as specified in the <code>Patient.contact.relationship</code> element. 

### Purpose 

This extension extends the Patient resource to support the exchange of the preferred ranking or order of contact applied to a contact on a Patient's contact list, which is currently not supported by the FHIR standard.
-->

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreContactRank'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Patient-88961,text:Patient.contact}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ContactRank}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ContactRank}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ContactRank}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ContactRank}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Contact Rank</b>- This example shows the extension which uses a PositiveInt to indicate the order that the people listed as contacts for the patient should be contacted. This example uses the value 1 to show that this is the first person who should be contacted.<br>
{{pagelink:Example-UKCore-Patient-Extension-ContactRank}}
<br><br>
</div>

---