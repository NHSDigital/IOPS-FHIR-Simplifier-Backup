---
topic: Profile-Observation-Group
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-Group-Lab
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-Group-Lab
---

# StructureDefinition {{variable:issue}}

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The <code>id</code> / <code>title</code> / <code>name</code> / <code>url</code> of this profile were changed in the STU2 Sequence release, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div>

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Full Blood count</b> - An example to illustrate a full blood count using multiple lab observation references.<br/>
{{pagelink:Example-UKCore-Observation-Group-FullBloodCount}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Group specific laboratory observations together, for example Full Blood Count,
- Place laboratory observations in an ordered fashion.
<br><br>
The Observation-LabGroup profile is used to reference multiple individual laboratory observations (UKCore-Observation-Lab) which together form a larger test set, for example a urea and electrolytes test that contains many several sub tests. 
<br><br>

<div id="renderParent" title="Dervied Lab profile structure">
{{render: Derived-Profiles-Lab-Example }}
</div>

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
<td><code>Observation.hasMember</code></td>
<td>Related resource that belongs to the Observation group</td>
</tr>
<tr>
<td><code>Observation.component</code></td>
<td>Component / sub results.</td>
</tr>
</table>
</div>

---
