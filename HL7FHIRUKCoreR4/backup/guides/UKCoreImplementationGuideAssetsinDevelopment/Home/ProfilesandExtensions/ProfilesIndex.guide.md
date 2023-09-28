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

##  Profiles in Development

<table id="assets">
<tr>
<th width="25%">Profile</th>
<th width="10%">Status</th>
<th width="10%">Maturity</th>
<th width="45%">Description</th>
<th width="10%">C&TA Sprint</th>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-AuditEvent">AuditEvent</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the AuditEvent resource for the minimal set of data to query and retrieve information about an event created to maintain a security log.</td>
<td>Not done yet</td>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Bundle">Bundle</a></td>
<td>draft</td>
<td>0</td>
<td>Defines a UK Core profile of a container for a collection of resources./td>
<td>Not done yet</td>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-CarePlan">CarePlan</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the CarePlan resource for the minimal set of data to query and retrieve a patient’s Care Plan.</td>
<td>Not done yet</td>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-CareTeam">CareTeam</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the CareTeam resource for the minimal set of data to query and retrieve an individual’s care team.</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Communication">Communication</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the List resource for the minimal set of data to query and retrieve a list of information</td>
<td>Not done yet</td>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Consent">Consent</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the Consent resource for the minimal set of data to query and retrieve consent information</td>
<td>Not done yet</td>
</tr>
<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Device">Device</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the Device resource for the minimal set of data to query and retrieve information relating to a type of a manufactured item that is used in the provision of healthcare without being substantially changed through that activity. The device may be a medical or non-medical device.</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-DiagnosticReport">DiagnosticReport</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the DiagnosticReport resource for the minimal set of data to query and retrieve diagnostic report information.</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-DocumentReference">DocumentReference</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the DocumentReference resource</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Observation">Observation</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the observation resource for the minimal set of data to query and retrieve generic observation information</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Provenance">Provenance</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the provenance resource for the minimal set of data to query and retrieve generic provenance information</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-Specimen">Specimen</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the UK Core constraints and extensions on the Specimen resource for the minimal set of data to query and retrieve specimen information</td>
<td>Not done yet</td>
</tr>

<tr>
<td><a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/profileukcore-VitalSigns-Observation">VitalSigns-Observation</a></td>
<td>draft</td>
<td>0</td>
<td>Defines the observation constraints and extensions on the UK Core observation resource for the minimal set of data to query and retrieve clinical vital signs observation information</td>
<td>Not done yet</td>
</tr>

</table>
















