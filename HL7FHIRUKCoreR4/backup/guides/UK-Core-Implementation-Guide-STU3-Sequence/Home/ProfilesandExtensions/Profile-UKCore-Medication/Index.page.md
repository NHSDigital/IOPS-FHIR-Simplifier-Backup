---
topic: Profile-Medication
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication
usage: http://hl7.org/fhir/StructureDefinition/Medication
issue: UKCore-Medication
---
# StructureDefinition-UKCore-Medication

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>COVID Vaccine</b> - An example to illustrate the batch element.  <br>
{{pagelink:Example-UKCore-Medication-COVID-Vaccine}}   <br><br>
<b>Medication Trade Family</b> - An example to illustrate the Medication Trade Family.  <br>
{{pagelink:Example-UKCore-Extension-MedicationTradeFamily}} <br><br>
<b>Timolol</b> - An example to illustrate the form element with a VTM.  <br>
{{pagelink:Example-UKCore-Medication-TimololVTM}}   <br><br>
<b>Timoptol Eye Drops</b> - An example to illustrate a representation of eye drops.  <br>
{{pagelink:Example-UKCore-Medication-TimoptolEyeDrops}}   <br><br>
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios

The UK Core Medication profile will likely not be used in isolation. It does not provide the context for the medication, e.g. the patient or medication related process. It will be typically used as a referenced resource within
- {{pagelink:Profile-MedicationAdministration}}
- {{pagelink:Profile-MedicationDispense}}
- {{pagelink:Profile-MedicationRequest}}
- {{pagelink:Profile-MedicationStatement}}

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
<td><code>Medication.code</code></td>
<td>Codes that identify this medication.</td>
</tr>
</table> 
</div>

---
