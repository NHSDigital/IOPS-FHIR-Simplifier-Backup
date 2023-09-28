## `ContactPoint`

Details for all kinds of technology-mediated contact points for a person or organization, including telephone, email, etc.

The Contact datatype has the following elements and this is an overview of the datatype with additional UK Core guidance. The full definition is available from the [FHIR standard](http://hl7.org/fhir/R4/datatypes.html#ContactPoint).


<table id="assets">
<tr>
<th>Element</th>
<th>type</th>
<th>Usage Guidance</th>
<th>Description</th>
</tr>
<tr>
<td><code>system</code></td>
<td>code</td>
<td>should be present</td>
<td>Details for all kinds of technology-mediated contact points for a person or organization, including telephone, email, etc. </td>
</tr>
<tr>
<td><code>value</code></td>
<td>string</td>
<td>must be present</td>
<td>The actual contact point details</td>
</tr>
<tr>
<td><code>use</code></td>
<td>code</td>
<td>may be present</td>
<td>Identifies the purpose for the contact point.</td>
</tr>
<tr>
<td><code>rank</code></td>
<td>positiveInt</td>
<td>may be present</td>
<td>Specifies a preferred order in which to use a set of contacts. ContactPoints with lower rank values are more preferred than those with higher rank values.</td>
</tr>
<tr>
<td><code>period</code></td>
<td>Period</td>
<td>may be present</td>
<td>Time period when the contact point was/is in use.</td>
</tr>
</table>

### Additional Information and Guidance
This section contains extra guidance and information about the use of this datatype in the UK Core FHIR implementations. 

### `system`
Identifies the type of system used for the contact point.

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/contact-point-system}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/contact-point-system}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/contact-point-system}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/contact-point-system}}
</div>

<br/>


### `use`
The use of the contact point is done using following codes

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/contact-point-use}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/contact-point-use}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/contact-point-use}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/contact-point-use}}
</div>

---



