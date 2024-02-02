---
topic: Profile-EpisodeOfCare
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare
usage: http://hl7.org/fhir/StructureDefinition/EpisodeOfCare
issue: UKCore-EpisodeOfCare
---
# StructureDefinition-UKCore-EpisodeOfCare

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Smoking Cessation Therapy</b> -An example to illustrate an episode of care for smoking cessation therapy.<br/>
{{pagelink:Example-UKCore-EpisodeOfCare-SmokingCessationTherapy}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core EpisodeOfCare profile:

- Query for information about an episode of care associated with a patient
- Record or update information about an episode of care for a patient

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
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
</div>

---