---
topic: England-Flag-PatientFlag
subject: https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag
usage: http://hl7.org/fhir/StructureDefinition/Flag
issue: England-Flag-PatientFlag
---

# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/Templates/Profile-Template.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<br>{{pagelink: RA-PatientFlag-Example}}
<br>{{pagelink: FGM-PatientFlag-Example}}
<br><br>

</div>
</nocheck>

## Data Mapping

| FHIR element                | Business data items |
|-
| Flag.subject                | Patient the Flag is for/about |
| Flag.category               |                     |
| Flag.code                   | Code from  https://fhir.nhs.uk/England/ValueSet/England-FlagCategoryPatient<br />e.g. 'national-reasonable-adjustment-flag'                    |
| Flag.contained:provenance   | Who created or removed the Flag, and when |
