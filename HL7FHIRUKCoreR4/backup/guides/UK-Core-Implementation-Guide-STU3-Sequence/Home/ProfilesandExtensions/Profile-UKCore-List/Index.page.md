---
topic: Profile-List
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-List
usage: http://hl7.org/fhir/StructureDefinition/List
issue: UKCore-List
---
# StructureDefinition-UKCore-List

{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<nocheck>
<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Empty List</b> - This example shows the use of an empty List to indicate that there is no content. This is not supposed to represent actual system behaviour.
  <br>{{pagelink:Example-UKCore-List-EmptyList}}
  <br><br>
  <b>Bundled Allergy List</b> - This example is an example FHIR Bundle that could be returned following a query for the allergies for a patient. Note: the use of List and Bundle is not mandated and is used to illustrate a possible use of the List Profile and is not expected system behaviour.<br>
  {{pagelink:Example-UKCore-Bundle-AllergyList}}
  <br><br>
  <b>List Warning Code</b> - An example to illustrate a warning being provided in a List resource.<br>
  {{pagelink:Example-UKCore-Extension-ListWarningCode}}
  <br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

## Example Usage Scenarios ##

The following are example usage scenarios for the UK Core List profile:

- A list of allergies for a Patient
- A list of current medication for a Patient
- Record or update a list of information for Patient

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>List.status</code></td>
<td>Indicates the current state of this list.</td>
</tr>
<tr>
<td><code>List.mode</code></td>
<td>How this list was prepared.</td>
</tr>
<tr>
<td><code>List.code</code></td>
<td>This code defines the purpose of the list - why it was created.</td>
</tr>
<tr>
<td><code>List.subject</code></td>
<td>The common subject (or patient) of the resources that are in the list if there is one.</td>
</tr>
</table>

</div>

---
