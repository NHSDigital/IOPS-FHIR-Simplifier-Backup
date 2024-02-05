---
topic: Profile-Schedule
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule
usage: http://hl7.org/fhir/StructureDefinition/Schedule
issue: UKCore-Schedule
---
# StructureDefinition-UKCore-Schedule

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Immunization</b> - An example to illustrate a schedule regarding an immunization.
<br>
{{pagelink:Example-UKCore-Schedule-Immunization}}
<br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Schedule profile:
- Query for details of a schedule
- Exchange schedule information within a FHIR document or message.

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
<td><code>Schedule.active</code></td>
<td>Whether this schedule is in active use.</td>
</tr>
<tr>
<td><code>Schedule.specialty</code></td>
<td>Type of specialty needed.</td>
</tr>
<tr>
<td><code>Schedule.actor</code></td>
<td>Resource(s) that availability information is being provided for.</td>
</tr>
<tr>
<td><code>Schedule.planningHorizon</code></td>
<td>Period of time covered by schedule.</td>
</tr>
</table>
</div
---
