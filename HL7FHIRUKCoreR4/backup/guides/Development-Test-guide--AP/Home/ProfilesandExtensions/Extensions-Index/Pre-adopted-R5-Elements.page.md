---
topic: Library-Extensions-PreAdopt
---
## Pre-adopted R5 Elements


The following <a href="https://hl7.org/fhir/versions.html#extensions" class="external">R5 elements</a> have been agreed as suitable to be included for use with the UK Core {{pagelink:Library-Profiles,text:Profiles}} because the use case for pre-adopting an R5 element as an Extension, rather than creating a UK Core specific extension is fully met.

As of 19/05/2023, the package to enable pre-adopted elements to function as per the guidance, is not available. To enable rendering and validation of these pre-adopted elements, we have provided UK Core proxy extensions, as per the current threads on <a href="https://chat.fhir.org/#narrow/stream/179166-implementers/topic/R5.20Extensions.20for.20R4.3F" class="external">chat.fhir.org</a>, with the R5 canonical urls. These proxy extensions will be retired once the HL7 package is released.

<table class="assets" title="Pre-adoptedFHIR R5 elements list and context of use details">
<tr>
<th>R5 Element</th>
<th>Related Profile</th>
<th>Proxy Extension</th>
<th>Modifier Extension</th>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R5/diagnosticreport-definitions.html#DiagnosticReport.composition" class="external">DiagnosticReport.composition</a></td>
<td>{{pagelink:Profile-DiagnosticReport}}</td>
<td>{{pagelink:Extension-UKCore-CompositionReference}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R5/diagnosticreport-definitions.html#DiagnosticReport.note" class="external">DiagnosticReport.note</a></td>
<td>{{pagelink:Profile-DiagnosticReport}}</td>
<td>{{pagelink:Extension-UKCore-Note}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R5/familymemberhistory-definitions.html#FamilyMemberHistory.participant" class="external">FamilyMemberHistory.participant</a></td>
<td>{{pagelink:Profile-FamilyMemberHistory}}</td>
<td>{{pagelink:Extension-UKCore-Participant}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R5/observation-definitions.html#Observation.triggeredBy" class="external">Observation.triggeredBy</a></td>
<td>{{pagelink:Profile-Observation}}</td>
<td>{{pagelink:Extension-UKCore-TriggeredBy}}</td>
<td>NO</td>
</tr>
<tr>
<td><a href="https://hl7.org/fhir/R5/specimen-definitions.html#Specimen.collection.collector" class="external">Specimen.collection.collector</a></td>
<td>{{pagelink:Profile-Specimen}}</td>
<td>{{pagelink:Extension-UKCore-collectionCollector}}</td>
<td>NO</td>
</tr>

</table>

---