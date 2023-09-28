## StructureDefinition Extension-England-ProvenanceAgent

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionEnglandProvenanceAgent'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-England-Task, text:Task}}
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
{{tree:https://fhir.nhs.uk/StructureDefinition/Extension-England-ProvenanceAgent}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/Extension-England-ProvenanceAgent}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/Extension-England-ProvenanceAgent}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/Extension-England-ProvenanceAgent}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b></b> There is currently no example that uses this extension. An example will be added in a future release. </br>
<br><br>
</div>

<br>

More information about the constraints on the <code>Extension-England-Provenance-Agent</code> can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-prov-agent-001</td>
<td>error</td>
<td>(reference.exists() or identifier.exists())</td>
<td>An identifier reference or resource reference must be provided.</td>
</tr>
<tr>
<td>nhse-prov-agent-002</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').value.matches('^[0-9]{2}[A-Z]{1}[0-9]{4}[A-Z]{1}$'))</td>
<td>NMC must be of the format NNANNNNA.</td>
</tr>
<tr>
<td>nhse-prov-agent-003</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').value.matches('^[G]{1}[01234589]{1}[0-9]{6}$'))</td>
<td>GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)</td>
</tr>
<tr>
<td>nhse-prov-agent-004</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').value.matches('^[C]{1}[0-9]{7}$'))</td>
<td>GMC must be of the format CNNNNNNN</td>
</tr>
<tr>
<td>nhse-prov-agent-005</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').value.matches('^[0-9]{7}$'))</td>
<td>GPHC must be of the format NNNNNNN</td>
</tr>
<tr>
<td>nhse-prov-agent-006</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').value.matches('^[A-Z]{2}[0-9]{6}$'))</td>
<td>HCPC must be of the format AANNNNNN</td>
</tr>
<tr>
<td>nhse-prov-agent-007</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').value.matches('^[0-9]{6}$'))</td>
<td>DIN format must be NNNNNN</td>
</tr>
<tr>
<td>nhse-prov-agent-008</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').value.matches('^[0-9]{12}$'))</td>
<td>SDS Role Profile Id must be 12 digits</td>
</tr>
</table>

---

 
