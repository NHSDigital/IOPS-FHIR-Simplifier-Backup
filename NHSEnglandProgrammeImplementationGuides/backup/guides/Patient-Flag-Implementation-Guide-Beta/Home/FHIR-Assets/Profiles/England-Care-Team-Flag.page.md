---
topic: England-CareTeam-Flag
subject: https://fhir.nhs.uk/England/StructureDefinition/England-CareTeam-Flag
usage: http://hl7.org/fhir/StructureDefinition/CareTeam
issue: England-CareTeam-Flag
---

# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/Templates/Profile-Template.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<br>{{pagelink: CPIS-Bundle-Example}}
<br>{{pagelink: CPIS-CareTeam-Example}}
<br><br>

</div>
</nocheck>


## Data Mapping

|FHIR Element|Description|Cardinality|Must Support|
|-
|CareTeam.id|Unique identifier for the CareTeam resource|0..1|Yes|
|CareTeam.status|The current status of the CareTeam (e.g., active, suspended)|1..1|Yes|
|CareTeam.name|Name of the care team (e.g., Local Authority Safeguarding Team))|1..1|Yes|
|CareTeam.telecom|Contact details for the CareTeam (e.g., email, phone)|1..*|No|
