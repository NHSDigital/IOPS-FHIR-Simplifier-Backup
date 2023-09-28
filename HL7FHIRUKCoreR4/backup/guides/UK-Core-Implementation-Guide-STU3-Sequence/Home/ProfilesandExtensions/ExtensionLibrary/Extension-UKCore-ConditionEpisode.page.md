---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-ConditionEpisode
---
## StructureDefinition Extension-UKCore-ConditionEpisode

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreConditionEpisode'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Condition,text:Condition}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Condition episode</b>- An example to illustrate the extension which is used to indicate the episodicity status of a condition.<br>
  {{pagelink:Example-UKCore-Extension-ConditionEpisode}}
</div>

<h3 id="guidance-conditionepisode">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-ConditionEpisodicity}}.

---