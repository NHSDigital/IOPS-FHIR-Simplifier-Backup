---
topic: Profile-EpisodeOfCare-32298
---
# StructureDefinition-UKCore-EpisodeOfCare

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreEpisodeOfCare'
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
	name = 'UKCoreEpisodeOfCare'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Smoking Cessation Therapy</b> -An example to illustrate an episode of care for smoking cessation therapy.<br/>
{{pagelink:Example-UKCore-EpisodeOfCare-SmokingCessationTherapy}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core EpisodeOfCare profile:

- Query for information about an episode of care associated with a patient
- Record or update information about an episode of care for a patient


## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>EpisodeOfCare.patient</code></td>
<td>The patient who is the focus of this episode of care.</td>
</tr>
<tr>
<td><code>EpisodeOfCare.period</code></td>
<td>The interval during which the managing organization assumes the defined responsibility.</td>
</tr>
<tr>
<td><code>EpisodeOfCare.careManager</code></td>
<td>The practitioner that is the care manager/care coordinator for this patient.</td>
</tr>
</table>

---