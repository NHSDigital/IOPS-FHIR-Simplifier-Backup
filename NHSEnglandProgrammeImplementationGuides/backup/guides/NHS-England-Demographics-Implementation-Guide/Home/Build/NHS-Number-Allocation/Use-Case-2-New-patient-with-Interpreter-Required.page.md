---
subject: PDS-Patient-AlbertEinsteinCommunication-Example
---

## {{page-title}}

<table><colgroup><col style="width: 16.3025%;"/><col style="width: 83.6914%;"/></colgroup><tbody><tr>
<td><strong>Name</strong></td><td>Allocate NHS Number</td>
</tr><tr>
<td><strong>Version</strong></td><td>0.1</td>
</tr><tr>
<td><strong>ID</strong></td><td>n/a</td></tr><tr><td><strong>Owner</strong></td><td>NHS England. <br>Team responsible for delivery – Demographics 101.</td>
</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td>Albert Einstein has returned to England after spending many years abroad. Albert has changed his name several times and can't remember any addresses he had in England. He does remember being in hospital as a child in Devon. Amy Armstrong tries several Queries using some of the names Albert has used over the years but she can find no record for Albert. She decides to allocate an NHS Number and completes the on screen record with the information that Albert provides, address, telephone, name, sex, date of birth. She also asks Albert for his preferences and adds his preferred contact method, preferred written communication format and preferred language and interpreter required. She also marks the record to say that Albert has had previous NHS contact. This is transmitted to PDS as a <a href="https://data.developer.nhs.uk/dms/mim/6.3.01/Domains/PDS/Document%20files/PDS%20IM.htm#_Toc_Section_6.9" class="external-link" rel="nofollow">PDS NHS Number Allocation Request</a> and a NHS number is allocated and returned via the <a href="https://data.developer.nhs.uk/dms/mim/6.3.01/Domains/PDS/Document%20files/PDS%20IM.htm#_Toc_Section_6.10" class="external-link" rel="nofollow">PDS NHS Number Allocation Request Accepted</a>.<strong>Summary:</strong><strong>As </strong>a healthcare professional,<strong>I can </strong>allocate an NHS Number if I can find no record for a patient,<strong>So that </strong>I can add the patient's personal details, preferences, and contact to his record for future use</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Healthcare professional (excluding GP), Patient, PDS</td>
</tr><tr>
<td><strong>Frequency of Use</strong></td><td>Used daily by multiple NHS trusts.</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Appointment where a healthcare professional tries to locate a patient’s record</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td><ol><li>Healthcare professional has access to PDS</li><li>All of the following items of patient demographic information are known: name, sex, birthdate, address</li></ol></td>
</tr><tr>
<td><strong>Post Conditions</strong></td><td><ol><li>The PDS processes the request and allocates an NHS number for the patient</li><li>A response, denoted as PDS NHS Number Allocation Request Accepted, is returned and received by the healthcare professional</li></ol></td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>Healthcare professional initiates a search for the patient’s existing record by inputting name, sex, birthdate, and address into PDS search</li><li>No patient record is found on the system</li><li>The healthcare professional decides to allocate an NHS Number to the patient</li><li>On the system interface, the healthcare professional completes the on-screen record with the information provided by the patient, including address, telephone, name, sex, and date of birth</li><li>Additional preferences from the patient are gathered, such as preferred contact method, preferred written communication format, preferred language, and whether an interpreter is required</li><li>The information is transmitted to the PDS as a PDS NHS Number Allocation Request along with the authority requesting (Registering authority is required for whoever is requesting the NHS Number)</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td><ol><li>PDS encounters technical issues when allocating number and an error is returned</li><li>Patient record with NHS number is returned on submitting a search</li><li>Multiple patient records are found and an error message is returned</li></ol></td></tr><tr><td><strong>Exception</strong></td><td>Healthcare professional omits required information (demographic data and registering authority) in the number allocation request which results in an error message being returned</td>
</tr></tbody></table>

### User Story Summary (Clinical Overview)
Albert Einstein has returned to England after spending many years abroad. Albert has changed his name several times and can't remember any addresses he had in England. He does remember being in hospital as a child in Devon. Amy Armstrong tries several Queries using some of the names Albert has used over the years but she can find no record for Albert. She decides to allocate an NHS Number and completes the on screen record with the information that Albert provides, address, telephone, name, sex, date of birth.

She also asks Albert for his preferences and adds his preferred contact method, preferred written communication format and preferred language and interpreter required. 

She also marks the record to say that Albert has had previous NHS contact. This is transmitted to PDS as a <a href="https://data.developer.nhs.uk/dms/mim/6.3.01/Domains/PDS/Document%20files/PDS%20IM.htm#_Toc_Section_6.9" class="external-link" rel="nofollow">PDS NHS Number Allocation Request</a> and a NHS number is allocated and returned via the <a href="https://data.developer.nhs.uk/dms/mim/6.3.01/Domains/PDS/Document%20files/PDS%20IM.htm#_Toc_Section_6.10" class="external-link" rel="nofollow">PDS NHS Number Allocation Request Accepted</a>.

{{page:Home/Templates/Example-Template.page.md}}

---

|wsessd|wewesd|sdsdds|
|--
|sdsd|sadssd|assdsd|
