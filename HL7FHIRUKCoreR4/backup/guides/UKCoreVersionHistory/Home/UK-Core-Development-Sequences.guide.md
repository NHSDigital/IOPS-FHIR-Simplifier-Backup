---
topic: Uk-core-dev-Seq-0f31814-417d-46fa-8ae3-bec132f819e8
---

<div id="toc_container">
<p class="toc_title">UK Core Sequences</p>
<ul class="toc_list">
  <li><a href="#Full">Full Development - The development history, work in progress and proposed development. It shows the development sequences. For each of the sequences it details the scope (list of profile), Clinical and Technical Assurance sprint and HL7 UK Ballot.</a>
  <ul>
  <li><a href="#STU3">STU3 Sequence -  The proposed development for STU3 it details the scope (list of profile), Clinical and Technical Assurance sprint and HL7 UK Ballot for this sequence.</a></li>
  <li><a href="#STU2">STU2 Sequence - The current development for STU2 it details the scope (list of profile), Clinical and Technical Assurance sprint and HL7 UK Ballot for this sequence.</a></li>
  <li><a href="#STU1">STU1 Sequence - The development to date for STU1 it details the scope (list of profile), Clinical and Technical Assurance sprint and HL7 UK Ballot for this sequence.</a></li>
  </ul>
</li>
</ul>
</div>

<h2 id="Full" align="center">Full Development</h2>

The diagram below illustrates the development history, work in progress and proposed development. It shows the development sequences. For each of the sequences it details the scope (list of profile), Clinical and Technical Assurance sprint and HL7 UK Ballot.

<div align="center">
<iframe src="https://drive.google.com/file/d/12uxYbTzAl6ECYYGr2VrpPKRa6a1So4fv/preview" width="988" height="800" allow="autoplay" title="UK Core Sequences and Versions" style="border:1"></iframe>
</div>


<h2 id="STU3" align="center">STU3 Sequence</h2>
The diagram below shows the development for the STU3 Sequence of UK Core.
{{render:stu3-sequence}}
<table id="assets">
<tr>
<th width="10%">Sequence</th>
<th width="10%">Status of this sequence</th>	
<th width="80%" colspan="2">Clinical & Technical Assurance and Ballot</th>
</tr>
<tr>
<td>STU3</td>
<td>Planned</td>
<td colspan="2">C&TA Sprint 6<br/>
 HL7 UK Ballot 3 (Proposed)<br/>
</td>
</tr>
<tr> 
<th colspan="4">Versions for this sequence</th>
</tr>
<th width="10%">Version</th>
<th width="10%">Status</th>	
<th width="40%">Clinical & Technical Assurance and Ballot</th>
<th width="40%">Profiles in Scope</th>
</tr>
<td>TBA</td>
<td>Planned</td>
<td>C&TA Sprint 6<br/>
 HL7 UK Ballot 3 (Proposed)<br/>
</td>
<td>
<ul>
<li>Consent </li>
<li>DiagnosticReport </li>
<li>FamilyMemberHistory </li>
<li>ImagingStudy </li>
<li>Observation </li>
<li>ServiceRequest </li>
<li>Specimen </li>
</ul>
</td>
</tr>
</table>

<h2 id="STU2" align="center">STU2 Sequence</h2>
The diagram below shows the development for the STU2 Sequence of UK Core.
{{render:stu2-sequence}}

<table id="assets">
<tr>
<th width="10%">Sequence</th>
<th width="10%">Status of this sequence</th>	
<th width="80%" colspan="2">Clinical & Technical Assurance and Ballot</th>
</tr>
<tr>
<td>STU2</td>
<td>Work in progress</td>
<td colspan="2">C&TA Sprint 4<br/>
C&TA Sprint 5<br/>
HL7 UK Ballot 2<br/>
</td>
</tr>
<tr> 
<th colspan="4">Versions for this sequence</th>
</tr>
<th width="10%">Version</th>
<th width="10%">Status</th>	
<th width="40%">Clinical & Technical Assurance and Ballot</th>
<th width="40%">Profiles in Scope</th>
</tr>
<td>1.1.0</td>
<td>Work in progress</td>
<td>C&TA Sprint 4<br/>C&TA Sprint 5<br/>
HL7 UK Ballot 2<br/></td>
<td>Sprint 4
<ul>
<li>Composition</li>
<li>Condition</li>
<li>Encounter</li>
<li>EpisodeOfCare</li>
<li>List</li>
<li>OperationOutcome</li>
<li>MessageHeader</li>
<li>Procedure</li>
<li>RelatedPerson</li>
</ul>
Sprint 5
<ul>
<li>Appointment</li>
<li>Flag</li>
<li>HealthcareService</li>
<li>Questionnaire</li>
<li>QuestionnaireResponse</li>
<li>Schedule</li>
<li>ServiceRequest</li>
<li>Slot</li>
<li>Task</li>
</td>
</tr>
</table>


<h2 id="STU1" align="center">STU1 Sequence</h2>
The diagram below shows the development for the STU1 Sequence of UK Core.
{{render:stu1-sequence}}
<br/>

<table id="assets">
<tr>
<th width="10%">Sequence</th>
<th width="10%">Status of this sequence</th>	
<th width="80%" colspan="2">Clinical & Technical Assurance and Ballot</th>
</tr>
<tr>
<td>STU1</td>
<td>Current</td>
<td colspan="2">C&TA Sprint 1<br/>
C&TA Sprint 2<br/>
C&TA Sprint 3<br/>
HL7 UK Ballot 1<br/>
</td>
</tr>
<tr> 
<th colspan="4">Versions for this sequence</th>
</tr>
<th width="10%">Version</th>
<th width="10%">Status</th>	
<th width="40%">Clinical & Technical Assurance and Ballot</th>
<th width="40%">Profiles in Scope</th>
</tr>
<td>1.0.0</td>
<td>Current</td>
<td>C&TA Sprint 1<br/>
C&TA Sprint 2<br/>
C&TA Sprint 3<br/>
HL7 UK Ballot 1<br/></td>
<td>Sprint 1
<ul>
<li>Location</li>
<li>Organization</li>
<li>Patient</li>
<li>Practitioner</li>
<li>PractitionerRole</li>
</ul>
Sprint 2
<ul>
<li>AllergyIntolerance</li>
</ul>
Sprint 3
<ul>
<li>Immunization</li>
<li>Medication</li>
<li>MedicationAdministration</li>
<li>MedicationDispense</li>
<li>MedicationStatement</li>
<li>MedicationRequest</li>
</ul>
*Note profiles from C&TA Sprint 4 and 5 were not part of Ballot 1 and were moved to the STU2 sequence
</td>
</tr>
</tr>
<td>0.5.0</td>
<td>Historical</td>
<td>C&TA Sprint 5</td>
<td>Sprint 5
<ul>
<li>Appointment</li>
<li>Flag</li>
<li>HealthcareService</li>
<li>Questionnaire</li>
<li>QuestionnaireResponse</li>
<li>Schedule</li>
<li>ServiceRequest</li>
<li>Slot</li>
<li>Task</li></td>
</tr>
</tr>
<td>0.4.0</td>
<td>Historical</td>
<td>C&TA Sprint 5</td>
<td>Sprint 5
<ul>
<li>Appointment</li>
<li>Flag</li>
<li>HealthcareService</li>
<li>Questionnaire</li>
<li>QuestionnaireResponse</li>
<li>Schedule</li>
<li>ServiceRequest</li>
<li>Slot</li>
<li>Task</li></td>
</tr>
</tr>
<td>0.3.0</td>
<td>Historical</td>
<td>C&TA Sprint 4</td>
<td>Sprint 4
<ul>
<li>Composition</li>
<li>Condition</li>
<li>Encounter</li>
<li>EpisodeOfCare</li>
<li>List</li>
<li>OperationOutcome</li>
<li>MessageHeader</li>
<li>Procedure</li>
<li>RelatedPerson</li>
</ul></td>
</tr>
</tr>
<td>0.2.0</td>
<td>Historical</td>
<td>C&TA Sprint 4</td>
<td>Sprint 4
<ul>
<li>Composition</li>
<li>Condition</li>
<li>Encounter</li>
<li>EpisodeOfCare</li>
<li>List</li>
<li>OperationOutcome</li>
<li>MessageHeader</li>
<li>Procedure</li>
<li>RelatedPerson</li>
</ul></td>
</tr>
</tr>
<td>0.1.0</td>
<td>Historical</td>
<td>C&TA Sprint 1<br/>
C&TA Sprint 2<br/>
C&TA Sprint 3<br/>
HL7 UK Ballot 1<br/></td>
<td>
Sprint 1
<ul>
<li>Location</li>
<li>Organization</li>
<li>Patient</li>
<li>Practitioner</li>
<li>PractitionerRole</li>
</ul>
Sprint 2
<ul>
<li>AllergyIntolerance</li>
</ul>
Sprint 3
<ul>
<li>Immunization</li>
<li>Medication</li>
<li>MedicationAdministration</li>
<li>MedicationDispense</li>
<li>MedicationStatement</li>
<li>MedicationRequest</li>
</ul>
</td>
</tr>
</table>




