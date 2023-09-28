---
topic: Library-Profiles-d78076a0-90d5-4e11-8b6e-64697b0bcfd9
---
## Profiles

The UK Core Profiles have been assigned a maturity level similar to the maturity levels described in the FHIR standard. This is intended to indicate how stable the Profile is deemed to be, this is in addition to the publication status of the Profile  <a href="http://hl7.org/fhir/valueset-publication-status.html" target="_blank">HL7 FHIR statuses</a> of draft, active, retired and unknown.

<br/>
<table id="assets">
<tr>
<th width="10%">Maturity level</th>
<th width="90%">Definition</th>
</tr>
<tr>
<td>0</td>
<td>The Profile has been published on the current build. This Profile has had no formal review and therefore may have quality issues. It is published only to allow the review process to start</td>
</tr>
<tr>
<td>1</td>
<td>The Profile produces no warnings during the build process and has had a formal internal review by the UK Core development team</td>
</tr>
<tr>
<td>2</td>
<td>The Profile has been released for review to the UK FHIR community, any feedback received has been addressed as far as possible</td>
</tr>
<tr>
<td>3</td>	
<td>The Profile has been presented for inclusion in the Technical and Clinical Assurance process</td>
</tr>
<tr>
<td>4</td>
<td>The Profile has completed the Technical and Clinical Assurance process and the status has been changed to active</td>
</tr>
<tr>
<td>5</td>
<td>The Profile has been presented for inclusion in the HL7 UK Ballot Process</td> 
</tr>
<tr> 
<td>6</td>
<td>The Profile has completed the HL7 UK Ballot process and is now deemed to be Normative</td>
</tr>
</table>
<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>
This Release 1 implementation guide only contains Profiles with a maturity level of 4 or more. Profiles that are at a earlier stage of development (maturity level of 0-2) are available in the <a href="https://simplifier.net/guide/UKCoreDevelopment2/Profiles" target="_blank"> HL7 FHIR® UK Core Profile  Implementation Guide R4 (Draft)</a><br/><br/>
The Profiles are rendered in several formats: 
<ul>
<li><b>Snapshot:</b> a fully calculated form of the structure that is not dependent on any other structure</li>
<li><b>Differential:</b> this describes only the differences that the Profile  makes relative to the structure definition (FHIR resource) they constrain</li> 
<li><b>Hybrid:</b> a hybrid view of the snapshot and differential views</li>
<li><b>Table:</b> a tabular view of the Profile  elements</li>
<li><b>XML:</b> a rendering of a XML view of the profile</li>
<li><b>JSON:</b> A rendering of a JSON view of the profile</li> 
</ul>
<br/>
<a href="http://hl7.org/fhir/profiling.html" target="_blank"> Further information from HL7 relating to profiling is available. </a>
</div>

<br/>
<table id="assets">
<tr>
<th width="25%">Profile</th>
<th width="10%">Status</th>
<th width="10%">Maturity</th>
<th width="45%">Description</th>
<th width="10%">C&TA Sprint</th>
</tr>
<tr>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the AllergyIntolerance resource for the minimal set of data to query and retrieve allergy information.</td>
<td>2</td>
</tr>
<tr>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Immunization resource for the minimal set of data to query and retrieve an individuals immunisation information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-Location-9738cf88-9ba3-4fc6-8efb-58b9583498f2}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Location resource for the minimal set of data to query and retrieve location information</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Medication resource for the minimal set of data to query and retrieve medication information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the MedicationAdministration resource for the minimal set of data to query and retrieve medication administration information</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the MedicationDispense resource for the minimal set of data to query and retrieve dispensed medication information.
</td>
<td>3</td>
<tr/>
<tr>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the MedicationRequest resource for the minimal set of data to query and retrieve prescription information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the MedicationStatement resource for the minimal set of data to query and retrieve medication statement information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Organization resource for the minimal set of data to query and retrieve organisation information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Patient resource for the minimal set of data to query and retrieve an individual’s demographic information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Practitioner resource for the minimal set of data to query and retrieve practitioner information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the PractitionerRole resource for the minimal set of data to query and retrieve practitioner role information.</td>
<td>1</td>
</tr>
</table>

<br/>













