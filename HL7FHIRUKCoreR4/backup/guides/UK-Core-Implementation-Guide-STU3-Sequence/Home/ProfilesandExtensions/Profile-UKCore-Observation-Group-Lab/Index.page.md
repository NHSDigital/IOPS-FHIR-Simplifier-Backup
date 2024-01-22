---
topic: Profile-Observation-Group
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-Group-L
---

# StructureDefinition-UKCore-Observation-Group-Lab

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Full Blood count</b> - An example to illustrate a full blood count using multiple lab observation references.<br/>
{{pagelink:Example-UKCore-Observation-Group-FullBloodCount}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Group specific laboratory observations together, for example Full Blood Count,
- Place laboratory observations in an ordered fashion.
<br><br>
The Observation-LabGroup profile is used to reference multiple individual laboratory observations (Observation-Lab) which together form a larger test set, for example a urea and electrolytes test that contains many several sub tests. 
<br><br>

<div id="renderParent" title="Dervied Lab profile structure">
{{render: Derived-Profiles-Lab-Example }}
</div>

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-Observation,text:UKCore-Observation}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

<h3>Minimum Viable Content</h3>

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} table, along with the following.

<table class="assets" title="Minimum Viable Content list">
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

---
