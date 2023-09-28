## StructureDefinition Extension-UKCore-Participant

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreParticipant'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-FamilyMemberHistory,text:FamilyMemberHistory}}</td>
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
{{tree:http://hl7.org/fhir/5.0/StructureDefinition/extension-FamilyMemberHistory.participant}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/5.0/StructureDefinition/extension-FamilyMemberHistory.participant}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/5.0/StructureDefinition/extension-FamilyMemberHistory.participant}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/5.0/StructureDefinition/extension-FamilyMemberHistory.participant}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Participant Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate the performer of the family member history related activity.<br>
  {{pagelink:Example-UKCore-Extension-Participant}}
  <br><br>
</div>

---