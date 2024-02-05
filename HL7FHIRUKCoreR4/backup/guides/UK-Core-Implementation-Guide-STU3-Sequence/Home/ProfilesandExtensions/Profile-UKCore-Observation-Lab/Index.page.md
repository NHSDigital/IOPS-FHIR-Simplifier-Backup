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


<div id="ProfileGuidance">

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


### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.status</code></td>
<td>The status of the result value.</td>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A code that classifies the general type of observation being made.</td>
</tr>
<tr>
<td><code>Observation.code</code></td>
<td>Type of observation (code / type)</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>Who and/or what the observation is about</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>Clinically relevant time/time-period for observation</td>
</tr>
<tr>
<td><code>Observation.performer</code></td>
<td>Who is responsible for the observation</td>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>Actual result.</td>
</tr>
<tr>
<td><code>Observation.component</code></td>
<td>Component / sub results.</td>
</tr>
</table>
</div>
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code><s>Observation.value[x]</s></code></td>
<td>Unlike the Observation profile, this derived profile it is not expected to use the <code>Observation.value[x]</code> element.</td>
</tr>
<tr>
<td><code>Observation.hasMember</code></td>
<td>Related resource that belongs to the Observation group</td>
</tr>
</table>
</div>

---

