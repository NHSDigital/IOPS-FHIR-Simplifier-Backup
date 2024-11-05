---
topic: England-Condition-Flag
subject: https://fhir.nhs.uk/England/StructureDefinition/England-Condition-Flag
usage: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition
issue: England-Condition-Flag
---

# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/Templates/Profile-Template.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<br>{{pagelink: RA-Condition-Example}}
<br>{{pagelink: RA-Condition2-Example}}
<br><br>

</div>
</nocheck>

## Data Mapping

| FHIR element                    | Business data items |
|-
| Condition.subject                    | Patient the Flag is for/about |
| Condition.category:patientFlag       | Code from https://fhir.nhs.uk/England/CodeSystem/PatientFlagCategory<br />e.g. 'national-reasonable-adjustment-flag' denotes as part of Reasonable Adjustment flag|
| Condition.category:conditionCategory | Code from https://fhir.nhs.uk/England/CodeSystem/England-ConditionCategoryRA<br />SHOULD usually use 'issue' |
| Condition.code                       | Code (Preferred) from https://fhir.nhs.uk/England/CodeSystem/England-ConditionCodeRA<br />– Identifies the Impairment Condition (optionally) recorded for which the Reasonable Adjustment is applied. The broad Impairment Condition categories enumerated in https://fhir.nhs.uk/England/CodeSystem/England-FlagCategoryRA<br /> are preferred, but specific coding, e.g. from SNOMED CT, may be used if desired.<br />– (Optionally) Identifies the UnderlyingCondition Condition recorded for which the Reasonable Adjustment is applied. Relevant SNOMED CT coding SHOULD be used to identify the UnderlyingCondition |
| Condition.contained:provenance   | Who created or removed the Flag, and when |