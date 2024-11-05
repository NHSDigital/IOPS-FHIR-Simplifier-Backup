---
topic: England-Flag-PatientFlag-Adjustment
subject: https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag-Adjustment
usage: http://hl7.org/fhir/StructureDefinition/Flag
issue: England-Flag-PatientFlag-Adjustment
---

# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/Templates/Profile-Template.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<br>{{pagelink:RA-Flag-Example}}
<br>{{pagelink:RA-Flag2-Example}}
<br><br>

</div>
</nocheck>

## Data Mapping

| FHIR element                    | Business data items |
|-
| Flag.subject                    | Patient the Flag is for/about |
| Flag.category:patientFlag       | Not currently in use       |
| Flag.category:programmeFlag     | Code from  https://fhir.nhs.uk/England/ValueSet/England-FlagCategoryPatient<br />e.g. 'national-reasonable-adjustment-flag' |
| Flag.code                       | Code from https://fhir.nhs.uk/England/ValueSet/England-FlagCodeRA                    |
                                      The code for the adjustment
| Flag.contained:provenance   | Who created or removed the Flag, and when |