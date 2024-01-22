---
topic: Profile-Observation-Lab
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Lab
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-Lab
---

# StructureDefinition-UKCore-Observation-Lab

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Query and retrieve a patient's laboratory observations
- Record or update a patient's laboratory observations
<br><br>
The Observation-Lab profile is for individual laboratory tests (Observation-Lab) which can be referenced by either Observation-LabGroup to form a larger test set, for example a urea and electrolyte test that contains many sub tests, or a DiagnosticReport-Lab as a single test within the report, for example Serum ferritin level.
<br><br>

<div id="renderParent" title="Dervied Lab profile structure">
{{render:Derived-Profiles-Lab-Example}}
</div>

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-Observation,text:UKCore-Observation}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

<h3>Minimum Viable Content</h3>

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} table.

---

