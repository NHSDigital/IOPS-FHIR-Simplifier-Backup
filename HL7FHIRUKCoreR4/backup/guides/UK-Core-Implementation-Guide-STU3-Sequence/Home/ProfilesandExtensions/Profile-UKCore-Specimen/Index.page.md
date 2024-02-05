---
topic: Profile-Specimen
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen
usage: http://hl7.org/fhir/StructureDefinition/Specimen
issue: UKCore-Specimen
---
# StructureDefinition-UKCore-Specimen

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Blood Specimen</b> - An example to illustrate a blood specimen for a patient.<br/>
{{pagelink:Example-UKCore-Specimen-BloodSpecimen}}
<br><br>
<b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to reference a Patient or RelatedPerson within Specimen.collection.collector.<br>
{{pagelink:Example-UKCore-Extension-CollectionCollector}}
<br><br>
<b>High Risk Specimen</b> - An example to illustrate using the HL7 core-defined Extension specimen-specialHandling to record why a specimen should be treated as a high risk.<br/>
{{pagelink:Example-UKCore-Extension-SpecialHandling}}
<br><br>
<b>Median Cubital Vein</b> - An example to illustrate the extension for a referenced body site.<br>
{{pagelink:Example-UKCore-Extension-BodySiteReference}}
<br><br>
<b>Sample Category</b> - An example to illustrate the extension to show the Genomics classification of a sample.<br>
{{pagelink:Example-UKCore-Extension-SampleCategory}}
<br><br>
<b>Urine Sample</b> - An example to illustrate a urine specimen for a patient.<br>
{{pagelink:Example-UKCore-Specimen-UrineSpecimen}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Specimen profile:

- Query for specimen information
- Exchange specimen information used in Observations and DiagnosticReport

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
<td><code>Specimen.status</code></td>
<td>The availability of the specimen.</td>
</tr>
<tr>
<td><code>Specimen.type</code></td>
<td>The kind of material that forms the specimen.</td>
</tr>
<tr>
<td><code>Specimen.subject</code></td>
<td>Where the specimen came from.</td>
</tr><tr>
<td><code>Specimen.receivedTime</code></td>
<td>The time when specimen was received for processing.</td>
</tr>
</table>
</div>

---