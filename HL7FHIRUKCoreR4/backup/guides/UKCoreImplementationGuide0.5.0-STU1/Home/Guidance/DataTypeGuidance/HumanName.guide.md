## `HumanName`

A name of a human with text, parts and usage information.

Names may be changed or repudiated. People may have different names in different contexts. Names may be divided into parts of different type that have variable significance depending on context, though the division into parts is not always significant. With personal names, the different parts might or might not be imbued with some implicit meaning; various cultures associate different importance with the name parts and the degree to which systems SHALL care about name parts around the world varies widely.

The HumanName datatype has the following elements and this is an overview of the datatype with additional UK Core guidance. The full definition is available from the [FHIR standard](http://hl7.org/fhir/R4/datatypes.html#HumanName).

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
<td>Identifies the purpose for this name. Allows the appropriate name for a particular context of use to be selected from among a set of names.Applications can assume that a name is current unless it explicitly says that it is temporary or old.</td>
</tr>
<td><code>text</code></td>
<td>string</td>
<td>may be present</td>
<td>Short description
Text representation of the full name. Specifies the entire name as it should be displayed e.g. on an application UI. This may be provided instead of or as well as the specific parts. Can provide both a text representation and parts. Applications updating a name SHALL ensure that when both text and parts are present, no content is included in the text that isn't found in a part.</td>
</tr>
<tr>
<td><code>family</code></td>
<td>string</td>
<td>should be present</td>
<td>Family name (often called 'Surname')</td>
</tr>
<tr>
<td><code>given</code></td>
<td>string</td>
<td>should be present</td>
<td>Given names (not always 'first'). Includes middle names. This repeating element order: Given Names appear in the correct order for presenting the name</td>
</tr>
<tr>
<td><code>prefix</code></td>
<td>string</td>
<td>may be present</td>
<td>Parts that come before the name. This repeating element order: Prefixes appear in the correct order for presenting the name</td>
</tr>
<tr>
<td><code>suffix</code></td>
<td>string</td>
<td>may be present</td>
<td>Parts that come after the name. This repeating element order: Suffixes appear in the correct order for presenting the name</td>
</tr>
<tr>
<td><code>period</code></td>
<td>Period</td>
<td>may be present</td>
<td>Time period when name was/is in use</td>
</tr>
</table>
<br/>


### Additional Information and Guidance
This section contains extra guidance and information about the use of this datatype in the UK Core FHIR implementations. 

### `use`
Identifies the purpose for this name.

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/name-use}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/name-use}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/name-use}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/name-use}}
</div>

<br/>

### Unstructured Names

`text`

Text representation of the name. This should only be used if a structured name as detailed below cannot be supported. It may be present in addition to a structured name.

### Structured Names
Structured names should be used whenever possible as detailed below.

The following elements should be used to construct structured names:

|element|example|
|--
|`family` |Smith|
| `given`  | John|
| `prefix` | Mr|	
| `suffix` | MBE|

---












