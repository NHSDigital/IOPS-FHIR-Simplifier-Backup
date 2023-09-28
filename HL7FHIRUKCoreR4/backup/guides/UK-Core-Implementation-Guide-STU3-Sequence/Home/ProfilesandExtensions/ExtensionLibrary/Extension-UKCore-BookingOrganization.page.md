---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-BookingOrganization
---
## StructureDefinition Extension-UKCore-BookingOrganization

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreBookingOrganization'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Appointment,text:Appointment}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Booking Organisation</b>- An example to illustrate the booking organisation extension associated with an appointment.<br>
{{pagelink:Example-UKCore-Extension-BookingOrganization}}
<br><br>
</div>

<h3 id="guidance-bookingorganization">Extension Specific Guidance</h3>
The resource being referenced SHALL conform to the following {{pagelink:Profile-Organization}}.

---
