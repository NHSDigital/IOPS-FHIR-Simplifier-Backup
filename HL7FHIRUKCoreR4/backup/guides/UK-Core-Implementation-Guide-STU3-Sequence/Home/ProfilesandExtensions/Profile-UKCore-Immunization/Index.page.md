---
topic: Profile-Immunization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization
usage: http://hl7.org/fhir/StructureDefinition/Immunization
issue: UKCore-Immunization
---
# StructureDefinition {{variable:issue}}

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Influenza virus vaccine</b> - An example to illustrate an Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization-InfluenzaVaccine}}
<br><br>
<b>Parent Present</b> - An example to illustrate the ParentPresent extension. <br>
{{pagelink: Example-UKCore-Extension-ParentPresent}}
<br><br>
<b>Vaccination Procedure</b> - An example to illustrate the VaccinationProcedure extension, with a vaccination procedure for an administered Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Extension-VaccinationProcedure}}
<br><br>
<b>Vaccination Procedure Covid</b> - An example to illustrate the VaccinationProcedureCovid extension, with a vaccination procedure for the COVID-19 Vaccine Vaxzevria.  <br>
{{pagelink: Example-UKCore-Extension-VaccinationProcedure-Covid}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Immunization profile:

- Query and retrieve an individual’s immunisations (vaccinations)
- Record or update an individual’s immunisations (vaccinations).

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
<td><code>Immunization.status</code></td>
<td>Indicates the current status of the immunization event.</td>
</tr>
<tr>
<td><code>Immunization.vaccineCode</code></td>
<td>Vaccine that was administered or was to be administered.</td>
</tr>
<tr>
<td><code>Immunization.patient</code></td>
<td>The patient who either received or did not receive the immunization.</td>
</tr>
<tr>
<td><code>Immunization.occurrence[x]</code></td>
<td>When the vaccine administered or was to be administered.</td>
</tr>
<tr>
<td><code>Immunization.manufacturer</code></td>
<td>Name of vaccine manufacturer.</td>
</tr>
<tr>
<td><code>Immunization.lotNumber</code></td>
<td>Lot number of the vaccine.</td>
</tr>
<tr>
<td><code>Immunization.doseQuantity</code></td>
<td>How much of the vaccine was administered</td>
</tr>
</table>


{{page:Home/ProfilesandExtensions/ProfileMustSupportTemplate.page.md}}

</div>

---
