---
topic: England-CarePlan-Flag
subject: https://fhir.nhs.uk/England/StructureDefinition/England-CarePlan-Flag
usage: http://hl7.org/fhir/StructureDefinition/CarePlan
issue: England-CarePlan-Flag
---

# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/Templates/Profile-Template.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<br>{{pagelink: CPIS-Bundle-Example}}
<br>{{pagelink: CPIS-CarePlan-Example}}
<br><br>

</div>
</nocheck>

## Data Mapping

|FHIR Element|Description|Cardinality|Must Support|
|-
|CarePlan.id|Unique identifier for the CarePlan resource|0..1|Yes|
|CarePlan.status|The current status of the CarePlan|1..1|Yes|
|CarePlan.category|Specifies the type of care plan (e.g., Child Protection Plan, LAC, UCP)|1..1|Yes|
|CarePlan.period|The timeframe during which the CarePlan is effective|1..1|Yes|
|CarePlan.careTeam|The team responsible for managing the CarePlan|1..*|Yes|

