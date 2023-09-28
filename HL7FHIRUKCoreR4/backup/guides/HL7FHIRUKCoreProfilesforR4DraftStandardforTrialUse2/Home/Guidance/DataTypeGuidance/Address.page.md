## `Address`

An address expressed using postal conventions (as opposed to GPS or other location definition formats). This data type may be used to convey addresses for use in delivering mail as well as for visiting locations which might not be valid for mail delivery. There are a variety of postal address formats defined around the world.

The Address datatype has the following elements and this is an overview of the datatype with additional UK Core guidance. The full definition is available from the [FHIR standard](http://hl7.org/fhir/R4/datatypes.html#Address).

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i> The address datatype has a UK Core extension {{pagelink:ExtensionUKCore-AddressKey-Index}}. This extension extends the Address datatype to support the exchange of the type of address key and the address key value.
</div>

<table id="assets">
<tr>
<th>Element</th>
<th>type</th>
<th>Usage Guidance</th>
<th>Description</th>
</tr>
<tr>
<td><code>use</code></td>
<td>code</td>
<td>should be present</td>
<td>purpose of this address</td>
</tr>
<tr>
<td><code>type</code></td>
<td>code</td>
<td>should be present</td>
<td>The type of address</td>
</tr>
<tr>
<td><code>text</code></td>
<td>string</td>
<td>may be present</td>
<td>Text representation of the address</td>
</tr>
<tr>
<td><code>line</code></td>
<td>string</td>
<td>should be present</td>
<td>Street name, number, direction & P.O. Box etc.This repeating element order: The order in which lines should appear in an address label</td>
</tr>
<tr>
<td><code>city</code></td>
<td>string</td>
<td>should be present</td>
<td>Name of city, town etc.</td>
</tr>
<tr>
<td><code>district</code></td>
<td>string</td>
<td>may be present</td>
<td>District name (aka county)</td>
</tr>
<tr>
<td><code>state</code></td>
<td>string</td>
<td>may be present</td>
<td>Sub-unit of country (abbreviations ok)</td>
</tr>
<tr>
<td><code>postalCode</code></td>
<td>string</td>
<td>should be present</td>
<td>Postal code for area</td>
</tr>
<tr>
<td><code>country</code></td>
<td>string</td>
<td>may be present</td>
<td>Country (e.g. can be ISO 3166 2 or 3 letter code)
</td>
</tr>
<tr>
<td><code>period</code></td>
<td>Period</td>
<td>may be present</td>
<td>Time period when the address was/is in use</td>
</tr>
</table>
<br/>

### Additional Information and Guidance
This section contains extra guidance and information about the use of this datatype in the UK Core FHIR implementations. 

### `use`
Purpose of this address.

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/address-use}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/address-use}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/address-use}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/address-use}}
</div>

<br/>

### `type`
The type of address.For example whether the address is a physical address and can be visited or is just a mailbox address. 

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/address-type}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/address-type}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/address-type}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/address-type}}
</div>
<br/>

### Unstructured Addresses

`text`

Text representation of the address. This should only be used if a structured address as detailed below cannot be supported. It may be present in addition to a structured address.

### Structured Addresses
Structured addresses should be used whenever possible as detailed below.

### `line`

Street name, number, direction & P.O. Box etc.
This repeating element order: The order in which lines should appear in an address label. Parts of the address that have distinct element listed below should not appear in the address line elements.

The following elements should be used to carry the associated information. 
- `city` - Name of city, town etc. 
- `district` - District name (aka county)
- `state` - Sub-unit of country (abbreviations ok)
- `Postal` - Code for area
- `country` - Country (e.g. can be ISO 3166 2 or 3 letter code).

---