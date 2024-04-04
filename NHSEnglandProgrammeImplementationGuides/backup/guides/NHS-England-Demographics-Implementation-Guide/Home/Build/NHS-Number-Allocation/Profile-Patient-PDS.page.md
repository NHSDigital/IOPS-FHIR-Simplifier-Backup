---
topic: Profile-England-Patient-PDS
subject: https://fhir.nhs.uk/England/StructureDefinition/England-Patient-PDS
usage: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient
issue: england-patient-pds
---
# StructureDefinition {{variable:issue}}

{{page:Home/Templates/Profile-Template.page.md}}

---
## Use Case

<table class="assets" title="PDS Use Case 1">
<td><strong>Name</strong></td><td>Create a record for a new patient</td>
</tr><tr>
<td><strong>Version</strong></td><td>0.1</td>
</tr><tr>
<td><strong>ID</strong></td><td>n/a</td></tr><tr><td><strong>Owner</strong></td><td>NHS England. <br>Team responsible for delivery – Demographics 101.</td>
</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> PDS FHIR user with Healthcare Worker Access <br><strong>I want</strong> a new NHS number to be allocated for individuals, when no existing NHS number exists <br><strong>So that</strong> the individual's medical information can be attached to an NHS number</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Healthcare professional (excluding GPs)</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Used daily by multiple NHS trusts.</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Secondary healthcare provider searches for an individual (likely using the 'Search for a patient' endpoint in the PDS FHIR API). If an NHS number is not found, then a request to allocate a new NHS number is submitted. <br><br>This process will not be used for allocating an NHS number for the following scenarios:<ol><li>For individuals requesting an NHS number via a primary healthcare (GP practice). Currently NHAIS is used for this use case. Likely use cases for requesting a new NHS number through primary care are adoption, gender reassignment, unhoused individuals seeking medical care, or a new NHS number being required due to domestic violence or witness protection.</li><li>As part of a birth registration. 'Birth Notice allocation' (BNA) in NCRS (National Care Record Service) or the 'Birth Notice allocation endpoint in PDS HL7 is used for this.</li><li>For a visitor or migrant to the UK. NHS number will be created as part of the Home Office immigration data feed.</li></ol></td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td><ol><li>Patient is seeking medical care.</li><li>Patient's demographics information is known, such as name address, and communication details.</li><li>Healthcare work has attempted to locate Patient but has been unable to find an existing NHS number.</li></ol></td></tr><tr><td><strong>Post Conditions</strong></td><td>Patient's medical data can be attached to a NHS number on local systems.</td>
</tr><tr>
<td><strong>Main Course</strong></td><td>If no NHS number exists for the submitted individual, a new NHS number is allocated and returned to the user.</td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>If a single NHS number exists for the supplied demographic data, then this found NHS number is returned to the user.</td></tr><tr><td><strong>Exception</strong></td><td>If multiple NHS numbers are found for the supplied demographic data, then an error message is returned to the user.</td>
</tr></tbody></table>

---
