## {{page-title}}


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> The content on these pages have not been approved or adopted by NHS England.</div>

Standards for Cross Enterprise Document Sharing API's are:

{{render:diagrams-TechnicalFramework-SharedClinicalDocuments-XDS}}


<table>
<thead>
 <th>Standards</th>
 <th>Put Document</th>
 <th>Register Document</th>
 <th>Get Document List</th>
 <th>Get Document</th>
</thead>
<tr>
  <td>NRL</td>
  <td></td>
  <td><a href="https://digital.nhs.uk/developer/api-catalogue/national-record-locator-producer-fhir#post-/DocumentReference"> Create new, or Supersede existing, document pointers</a></td>
  <td><a href="https://digital.nhs.uk/developer/api-catalogue/national-record-locator-producer-fhir#get-/DocumentReference"> Retrieve document pointers</a></td>
  <td></td>
</tr>
<tr>
  <td>IHE XDS</td>
  <td> <a href="https://profiles.ihe.net/ITI/TF/Volume2/ITI-41.html#3.41">Provide and Register Document Set-b [ITI-41]</a> </td>
  <td> <a href="https://profiles.ihe.net/ITI/TF/Volume2/ITI-42.html#3.42">Register Document Set-b [ITI-42]</a></td>
  <td><a href="https://profiles.ihe.net/ITI/TF/Volume2/ITI-18.html#3.18">Registry Stored Query [ITI-18]</a></td>
  <td><a href="https://profiles.ihe.net/ITI/TF/Volume2/ITI-43.html#3.43">Retrieve Document Set [ITI-43]</a></td>
</tr>
<tr>
  <td>IHE MHD (FHIR R4)</td>
  <td><a href="https://profiles.ihe.net/ITI/MHD/ITI-105.html">Simplified Publish [ITI-105]  </a> <br/> <a href="https://profiles.ihe.net/ITI/MHD/ITI-105.html">Provide Document Bundle [ITI-65] </a></td>
  <td><a href=""> </a></td>
  <td><a href="https://profiles.ihe.net/ITI/MHD/ITI-67.html"> Find Document References [ITI-67]</a></td>
  <td><a href="https://profiles.ihe.net/ITI/MHD/ITI-68.html"> Retrieve Document [ITI-68]</a></td>
</tr>
<tr>
  <td>HL7 v2</td>
  <td><a href="https://hl7-definition.caristix.com/v2/HL7v2.4/TriggerEvents/MDM_T02">MDM_T02 - Original document notification and content </a></td>
  <td><a href="https://hl7-definition.caristix.com/v2/HL7v2.4/TriggerEvents/MDM_T01"> MDM_T01 - Original document notification</a></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>HL7 FHIR</td>
  <td>HTTP POST (POST /Binary) <br/> POST /DocumentReference</td>
  <td>POST /DocumentReference</td>
  <td>GET /DocumentReference</td>
  <td>HTTP GET (GET /Binary)</td>
</tr>
</table>

