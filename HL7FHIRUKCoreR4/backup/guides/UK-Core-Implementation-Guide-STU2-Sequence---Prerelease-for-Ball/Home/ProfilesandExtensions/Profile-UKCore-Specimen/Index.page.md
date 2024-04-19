---
topic: Profile-Specimen-37178
---

# StructureDefinition-UKCore-Specimen

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreSpecimen'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'UKCoreSpecimen'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Blood Specimen</b> - An example to illustrate a blood specimen for a patient.<br/>
{{pagelink:Example-UKCore-Specimen-BloodSpecimen}}
<br><br>
<b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to reference a Patient or RelatedPerson within Specimen.collection.collector.<br>
{{pagelink:Example-UKCore-Specimen-Extension-CollectionCollector}}
<br><br>
<b>High Risk Specimen</b> - An example to illustrate using the HL7 core-defined Extension specimen-specialHandling to record why a specimen should be treated as a high risk.<br/>
{{pagelink:Example-UKCore-Specimen-Extension-SpecialHandling}}
<br><br>
<b>Median Cubital Vein</b> - An example to illustrate the extension for a referenced body site.<br>
{{pagelink:Example-UKCore-Specimen-Extension-BodySiteReference}}
<br><br>
<b>Sample Category</b> - An example to illustrate the extension to show the Genomics classification of a sample.<br>
{{pagelink:Example-UKCore-Specimen-Extension-SampleCategory}}
<br><br>
<b>Urine Sample</b> - An example to illustrate a urine specimen for a patient.<br>
{{pagelink:Example-UKCore-Specimen-UrineSpecimen}}
</div>

</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Specimen profile:

- Query for specimen information
- Exchange specimen information used in Observations and DiagnosticReport

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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
<td>The time when the specimen was received for processing.</td>
</tr>
</table>

---