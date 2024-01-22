---
topic: Profile-Observation-VitalSigns-BodyTemperature
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BodyTemperature
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-VitalSigns-BodyTemperature
---

# StructureDefinition-UKCore-Observation-VitalSigns-BodyTemperature

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BodyTemperature/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BodyTemperature</a>.
</div>

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Body Temperature</b> - An example to illustrate recording a patients temperature.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BodyTemperature}}<br><br>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation Vital Signs Body Temperature profile:

- Query and retrieve a patient's temperature
- Record or update a patient's body temperature

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

The UKCore-Observation-VitalSigns-BodyTemperature further derives from UKCore-Observation-VitalSigns, and this section only shows the differences between the two.

### Minimum Viable Content

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity SHALL be present.</td>
</tr>
</table>

---