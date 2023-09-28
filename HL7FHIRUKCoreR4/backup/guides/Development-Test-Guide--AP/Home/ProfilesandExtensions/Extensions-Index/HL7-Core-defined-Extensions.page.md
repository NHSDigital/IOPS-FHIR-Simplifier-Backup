---
topic: Library-Extensions-HL7
---
## {{page-title}}

The following [HL7 Core-defined Extensions](http://hl7.org/fhir/R4/extensibility-registry.html) have been agreed as suitable to be included for use with the UK Core {{pagelink:Library-Profiles,text:Profiles}} because the use case for an Extension is fully met by a pre-existing HL7 Core-defined Extension.

Implementers of the UK Core profiles MAY also use other HL7 core-defined extensions to extend the UK Core if required by the local implementation, but are encouraged to engage with the UK Core development process to add guidance into the UK Core for wider use by the UK FHIR Community.

<table class="assets">
<tr>
<th>HL7 Core-defined Extension</th>
<th>Context of Use</th>
<th>Related Profile</th>
<th>Modifier Extension</th>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-coding-sctdescid.html">Extension coding-sctdescid</a></td>
<td>Coding</td>
<td>Use on Element ID Coding</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-messageheader-response-request.html">Extension messageheader-response-request</a></td>
<td>MessageHeader</td>
<td>{{pagelink:Profile-MessageHeader}}</td>
<td>NO</td>
</tr>
<tr>            
<td><a href="https://hl7.org/fhir/R4/extension-organization-period.html">Extension organization-period</a></td>
<td>Organization</td>
<td>{{pagelink:Profile-Organization}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-patient-birthPlace.html">Extension patient-birthPlace</a></td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-patient-birthTime.html">Extension patient-birthTime</a></td>
<td>Patient.birthDate</td>
<td>{{pagelink:Profile-Patient}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-patient-cadavericDonor.html">Extension patient-cadavericDonor</a></td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-patient-interpreterRequired.html">Extension patient-interpreterRequired</a></td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R4/extension-specimen-specialhandling.html">Extension specimen-specialHandling</a></td>
<td>Specimen.collection</td>
<td>{{pagelink:Profile-Specimen}}</td>
<td>NO</td>
</tr>

</table>

---