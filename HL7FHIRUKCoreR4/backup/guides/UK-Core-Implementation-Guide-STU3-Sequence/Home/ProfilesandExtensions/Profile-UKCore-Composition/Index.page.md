---
topic: Profile-Composition
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition
usage: http://hl7.org/fhir/StructureDefinition/Composition
issue: UKCore-Composition
---

# StructureDefinition-UKCore-Composition

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Discharge</b> - An example to illustrate a composition containing a discharge summary.<br/>
{{pagelink:Example-UKCore-Composition-Discharge}}
<br/><br/>
<b>CareSetting Type</b> - An example to illustrate the care setting of a FHIR document.<br/>
{{pagelink:Example-UKCore-Extension-CareSettingType}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Composition profile:

- Query for a specific patient document or document type
- Query for recent patient documents
- Create a new document or update an existing document 

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
<td><code>Composition.status</code></td>
<td>The workflow/clinical status of this composition.</td>
</tr>
<tr>
<td><code>Composition.type</code></td>
<td>Specifies the particular kind of composition.</td>
</tr>
<tr>
<td><code>Composition.subject</code></td>
<td>Who and/or what the composition is about.</td>
</tr>
<tr>
<td><code>Composition.author</code></td>
<td>Identifies who is responsible for the information in the composition.</td>
</tr>
<tr>
<td><code>Composition.confidentiality</code></td>
<td>The code specifying the level of confidentiality of the Composition.</td>
</tr>
<tr>
<td><code>Composition.custodian</code></td>
<td>Identifies the organization or group who is responsible for ongoing maintenance of and access to the composition/document information.</td>
</tr>
</table>
</div>

---
