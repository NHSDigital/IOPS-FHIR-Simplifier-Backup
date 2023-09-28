---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AddressKey
---
## StructureDefinition Extension-UKCore-AddressKey

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAddressKey'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>Address</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Address Key</b>- An example to illustrate how the address key information is carried in a patient example. </br>
{{pagelink:Example-UKCore-Extension-AddressKey}}
<br><br>
</div>

<h3 id="guidance-addresskey">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-AddressKeyType}}.

---
