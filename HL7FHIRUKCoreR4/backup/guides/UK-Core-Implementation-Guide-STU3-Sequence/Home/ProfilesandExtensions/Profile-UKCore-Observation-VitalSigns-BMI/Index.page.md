---
topic: Profile-Observation-VitalSigns-BMI
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BMI
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-VitalSigns-BMI
---

# StructureDefinition-UKCore-Observation-VitalSigns-BMI

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BMI/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BMI</a>.
</div>

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Body Mass Index</b> - An example to illustrate recording a obese body mass index.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BMI}}<br><br>
</div>
</nocheck>

<div id="ProfileGuidance">


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation Vital Signs BMI profile:

- Query and retrieve a patient's body mass index
- Record or update a patient's body mass index

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

The UKCore-Observation-VitalSigns-BMI profile further derives from {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} and this page only shows the differences between the two. Refer to {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} for more implementation guidance.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} tables, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity or centile SHALL be present.</td>
</tr>
</table>
</div>

---