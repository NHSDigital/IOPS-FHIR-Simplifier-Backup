## StructureDefinition Extension-UKCore-DeliveryChannel

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDeliveryChannel'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Appointment-87479,text:Appointment}}<br/>
{{pagelink:Profile-Slot-83549,text:Slot}}</td>
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeliveryChannel}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeliveryChannel}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeliveryChannel}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeliveryChannel}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Delivery Channel</b>- An example to illustrate the delivery channel associated with an appointment.<br>
{{pagelink:Example-UKCore-Appointment-Extension-DeliveryChannel}}
<br><br>
</div>

### Guidance
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-DeliveryChannel}}.

---
