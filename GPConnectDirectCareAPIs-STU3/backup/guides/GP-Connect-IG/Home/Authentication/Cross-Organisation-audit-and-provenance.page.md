## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">Cross-organisation audit and provenance</h1>
</div>




 <div class="jwt-page">


<div class="post-content">

   
 <div class="summary"><b>Summary: </b>Overview of how audit and provenance data transported over GP Connect FHIR interfaces</div>
   

   

    
    
<!-- this handles the automatic toc. use ## for subheads to auto-generate the on-page minitoc. if you use html tags, you must supply an ID for the heading element in order for it to appear in the minitoc. -->
<script>
$( document ).ready(function() {
  // Handler for .ready() called.

$('#toc').toc({ minimumHeaders: 0, listType: 'ul', showSpeed: 0, headers: 'h2,h3,h4' });

/* this offset helps account for the space taken up by the floating toolbar. */
$('#toc').on('click', 'a', function() {
  var target = $(this.getAttribute('href'))
    , scroll_target = target.offset().top

  $(window).scrollTop(scroll_target - 10);
  return false
})
  
});
</script>

<div id="toc"></div>

    

  <h2 id="governance">Governance</h2>

<p>Provider systems <strong>SHALL</strong> ensure that access to confidential data, including patient or clinical data, through the API must meet, as a minimum, the same requirements for information governance (IG), authentication and authorisation, and auditing as that of the host system the API exposes.</p>

<h2 id="audit-trail">Audit trail</h2>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> As the GP Connect APIs are commissioned under the GPSoC framework, provider and consumer systems are expected to follow the standard ‘IG Requirements for GP Systems V4’ and ‘GP Systems Interface Mechanism’ requirements.</div>

<p>For implementers that don’t have access to the GPSoC Framework / ‘IG Requirements for GP Systems V4’ requirements then the following extract of requirements covers the main audit trail requirements:</p>

<ul>
  <li>
    <p>provider systems <strong>SHALL</strong> record in an audit trail all access and data changes within the system as a result of API activity in the same way that internal access and changes are required to be recorded</p>
  </li>
  <li>
    <p>provider systems <strong>SHALL</strong> ensure that all API transactions are recorded in an audit trail and that audit trails must be subject to the standard IG audit requirements as defined in ‘IG Requirements for GP Systems V4’ or as subsequently amended</p>
  </li>
  <li>
    <p>provider systems <strong>SHALL</strong> ensure failed or rejected API transactions are recorded with the same detail as for successful API requests, with error codes as per the <a href="development_fhir_error_handling_guidance.html">error handling guidance</a></p>
  </li>
</ul>

<p>Audit trail records <strong>SHALL</strong> include the following minimum information:</p>

<ul>
  <li>a record of the user identity - this is the User ID, Name, Role profile (including Role and Organisation, URP id when Smartcard authenticated) attribute values, obtained from the user’s session structure</li>
  <li>a record of the identity of the authority – the person authorising the entry of or access to data (if different from the user)</li>
  <li>the date and time on which the event occurred</li>
  <li>details of the nature of the audited event and the identity of the associated data (for example, patient ID, message ID) of the audited event</li>
  <li>a sequence number to protect against malicious attempts to subvert the audit trail by, for example, altering the system date</li>
  <li>audit trail records <strong>SHOULD</strong> include details of the end-user device (or system) involved in the recorded activity</li>
</ul>

<p>Audit trails <strong>SHALL</strong> be enabled at all times and there shall be no means for users, or any other individuals, to disable any audit trail.</p>

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> Whilst some details (such as name, role) associated with individual users are likely to change over time, the display of user information must reflect the state of such information as it was at the time of the associated event (such as data entry).</div>

<h2 id="provenance">Provenance</h2>

<p>Provider systems <strong>SHALL</strong> ensure that all additions, amendments or logical deletions to administrative and clinical data made via an API is clearly identified with information regarding the provenance of the data (such as timestamp, details of consumer system, details of user (including role)), so it is clear which information has been generated through an API rather than through the provider system itself.</p>

<p>Provider systems <strong>SHALL</strong> record the following provenance details of all API personal and sensitive personal data recorded within the system:</p>

<ul>
  <li>author details (identified through unique ID), including name and role</li>
  <li>data entered by (if different from author)</li>
  <li>date and time (to the second) entered</li>
  <li>originating organisation</li>
  <li>API interaction</li>
</ul>

<h2 id="legal-processing">Legal processing</h2>

<p>Provider systems <strong>SHALL</strong> ensure that data provided to consumer systems only includes data for which the GP practice acts as data controller.</p>

<h2 id="patient-demographic-cross-checking">Patient demographic cross-checking</h2>

<p>Consumer systems <strong>SHALL</strong> always perform a patient demographic check as part of the use of a GP Connect capability to ensure that the patient for whom the information has been provided is the same patient for whom the request was made, and make clear to the end user any discrepancies.</p>

<h2 id="cross-organisation-audit-and-provenance-transport">Cross-organisation audit and provenance transport</h2>

<h3 id="bearer-token">Bearer token</h3>

<p>Consumer systems <strong>SHALL</strong> provide audit and provenance details in the HTTP <code class="highlighter-rouge">Authorization</code> header as an OAuth Bearer Token (as outlined in <a href="https://tools.ietf.org/html/rfc6749">RFC 6749</a> in the form of a JSON Web Token (JWT) as defined in <a href="https://tools.ietf.org/html/rfc7519">RFC 7519</a>.</p>

<p>An example such an HTTP header is given below:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>     Authorization: Bearer jwt_token_string
</code></pre></div></div>

<p>Provider systems <strong>SHALL</strong> respond to OAuth Bearer Token errors in line with <a href="https://tools.ietf.org/html/rfc6750#section-3.1">RFC 6750 - section 3.1</a>.</p>

<p>It is highly recommended that standard libraries are used for creating the JWT as constructing and encoding the token manually may lead to issues with parsing the token. A good source of information about JWT and libraries to use can be found on the <a href="https://jwt.io/">JWT.io site</a>.</p>

<h3 id="jwt-generation">JWT generation</h3>

<p>Consumer system <strong>SHALL</strong> generate a new JWT for each API request. The consumer generated JWT <strong>SHALL</strong> consist of three <a href="https://tools.ietf.org/html/rfc4648#section-5">base64url encoded</a> parts separated by dots <code class="highlighter-rouge">.</code>, which are:</p>

<ul>
  <li>header</li>
  <li>payload</li>
  <li>signature</li>
</ul>

<h4 id="header">Header</h4>
<p>Consumer systems <strong>SHALL</strong> generate an unsecured JWT using the ‘none’ algorithm parameter in the header to indicate that no digital signature or MAC has been performed (please refer to section 6 of <a href="https://tools.ietf.org/html/rfc7519" target="_blank">RFC 7519</a>_ for details).</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"alg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"none"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"typ"</span><span class="p">:</span><span class="w"> </span><span class="s2">"JWT"</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="payload">Payload</h4>

<p>Consumers systems <strong>SHALL</strong> generate a JWT payload conforming to the requirements set out in the <a href="#jwt-payload">JWT Payload</a> section of this page.</p>

<h4 id="signature">Signature</h4>

<p>Consumer systems <strong>SHALL</strong> generate an empty signature.</p>

<h4 id="complete-jwt">Complete JWT</h4>

<p>The final output is three <a href="https://tools.ietf.org/html/rfc4648#section-5">base64url</a> encoded strings separated by dots (note: there is some canonicalisation done to the JSON before it is base64url encoded, which the JWT code libraries will do for you).</p>

<div class="language-shell highlighter-rouge"><div class="highlight"><pre class="highlight"><code>eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJpc3MiOiJodHRwOi8vZWMyLTU0LTE5NC0xMDktMTg0LmV1LXdlc3QtMS5jb21wdXRlLmFtYXpvbmF3cy5jb20vIy9zZWFyY2giLCJzdWIiOiIxIiwiYXVkIjoiaHR0cHM6Ly9hdXRob3JpemUuZmhpci5uaHMubmV0L3Rva2VuIiwiZXhwIjoxNDgxMjUyMjc1LCJpYXQiOjE0ODA5NTIyNzUsInJlYXNvbl9mb3JfcmVxdWVzdCI6ImRpcmVjdGNhcmUiLCJyZXF1ZXN0ZWRfcmVjb3JkIjp7InJlc291cmNlVHlwZSI6IlBhdGllbnQiLCJpZGVudGlmaWVyIjpbeyJzeXN0ZW0iOiJodHRwOi8vZmhpci5uaHMubmV0L0lkL25ocy1udW1iZXIiLCJ2YWx1ZSI6IjkwMDAwMDAwMzMifV19LCJyZXF1ZXN0ZWRfc2NvcGUiOiJwYXRpZW50LyoucmVhZCIsInJlcXVlc3RpbmdfZGV2aWNlIjp7InJlc291cmNlVHlwZSI6IkRldmljZSIsImlkIjoiMSIsImlkZW50aWZpZXIiOlt7InN5c3RlbSI6IldlYiBJbnRlcmZhY2UiLCJ2YWx1ZSI6IkdQIENvbm5lY3QgRGVtb25zdHJhdG9yIn1dLCJtb2RlbCI6IkRlbW9uc3RyYXRvciIsInZlcnNpb24iOiIxLjAifSwicmVxdWVzdGluZ19vcmdhbml6YXRpb24iOnsicmVzb3VyY2VUeXBlIjoiT3JnYW5pemF0aW9uIiwiaWQiOiIxIiwiaWRlbnRpZmllciI6W3sic3lzdGVtIjoiaHR0cDovL2ZoaXIubmhzLm5ldC9JZC9vZHMtb3JnYW5pemF0aW9uLWNvZGUiLCJ2YWx1ZSI6IltPRFNDb2RlXSJ9XSwibmFtZSI6IkdQIENvbm5lY3QgRGVtb25zdHJhdG9yIn0sInJlcXVlc3RpbmdfcHJhY3RpdGlvbmVyIjp7InJlc291cmNlVHlwZSI6IlByYWN0aXRpb25lciIsImlkIjoiMSIsImlkZW50aWZpZXIiOlt7InN5c3RlbSI6Imh0dHA6Ly9maGlyLm5ocy5uZXQvc2RzLXVzZXItaWQiLCJ2YWx1ZSI6IkcxMzU3OTEzNSJ9LHsic3lzdGVtIjoibG9jYWxTeXN0ZW0iLCJ2YWx1ZSI6IjEifV0sIm5hbWUiOnsiZmFtaWx5IjpbIkRlbW9uc3RyYXRvciJdLCJnaXZlbiI6WyJHUENvbm5lY3QiXSwicHJlZml4IjpbIk1yIl19fX0.
</code></pre></div></div>

<p><strong>Note</strong>: the final section (the signature) is empty, so the JWT will end with a trailing <code class="highlighter-rouge">.</code> (this must not be omitted, otherwise it would be an invalid token)</p>

<h3 id="jwt-payload">JWT payload</h3>

<p>Consumers <strong>SHALL</strong> populate the payload section of the JWT with the following claims:</p>

<ul>
  <li><a href="#iss-issuer-claim"><code class="highlighter-rouge">iss</code></a> (issuer)</li>
  <li><a href="#sub-subject-claim"><code class="highlighter-rouge">sub</code></a> (subject)</li>
  <li><a href="#aud-audience-claim"><code class="highlighter-rouge">aud</code></a> (audience)</li>
  <li><a href="#exp-expiry-claim"><code class="highlighter-rouge">exp</code></a> (expiry)</li>
  <li><a href="#iat-issued-at-claim"><code class="highlighter-rouge">iat</code></a> (issued at)</li>
  <li><a href="#reason_for_request-claim"><code class="highlighter-rouge">reason_for_request</code></a></li>
  <li><a href="#requested_scope-claim"><code class="highlighter-rouge">requested_scope</code></a></li>
  <li><a href="#requesting_device-claim"><code class="highlighter-rouge">requesting_device</code></a></li>
  <li><a href="#requesting_organization-claim"><code class="highlighter-rouge">requesting_organization</code></a></li>
  <li><a href="#requesting_practitioner-claim"><code class="highlighter-rouge">requesting_practitioner</code></a></li>
</ul>

<p>Please see details below on how to populate each claim.</p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> The JWT payload used in <strong>GP Connect API 0.x (DSTU2)</strong> is different to that displayed on this page.  Please ensure you consult the relevant specification from the <a href="https://developer.nhs.uk/gp-connect-specification-versions/">GP Connect specifications page</a> when constructing the JWT for different GP Connect API major versions.</div>

<hr />

<h4 id="iss-issuer-claim"><code class="highlighter-rouge">iss</code> (issuer) claim</h4>

<p>Consumer systems token issuer URI.</p>

<p>As the consuming system is presently responsible for generating the access token, this <strong>SHALL</strong> contain the URL of the Spine endpoint of the consumer system.</p>

<p>In future OAuth2 implementation, the <code class="highlighter-rouge">iss</code> claim will contain the URL of the OAuth2 authorisation server token endpoint.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"iss": "https://consumersupplier.thirdparty.nhs.uk/"</code></p>

<hr />

<h4 id="sub-subject-claim"><code class="highlighter-rouge">sub</code> (subject) claim</h4>

<p>ID for the user on whose behalf this request is being made. Matches <a href="#requesting_practitioner-claim"><code class="highlighter-rouge">requesting_practitioner.id</code></a>.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"sub": "10019"</code></p>

<hr />

<h4 id="aud-audience-claim"><code class="highlighter-rouge">aud</code> (audience) claim</h4>

<p>The <a href="development_general_api_guidance.html#service-root-url">service root URL</a> of the provider system.</p>

<p>This is the value returned from the <a href="integration_spine_directory_service.html">SDS endpoint lookup service</a> in the <code class="highlighter-rouge">nhsMhsEndPoint</code> field.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"aud": "https://providersupplier.thirdparty.nhs.uk/GP0001/STU3/1"</code></p>

<hr />

<h4 id="exp-expiry-claim"><code class="highlighter-rouge">exp</code> (expiry) claim</h4>

<p>Identifies the expiration time in UTC on and after which the JWT <strong>SHALL NOT</strong> be accepted for processing.</p>

<p>The expiration time <strong>SHALL</strong> be set to 5 minutes after the token creation time (populated in the <a href="#iat-issued-at-claim"><code class="highlighter-rouge">iat</code> claim</a>).</p>

<p>The value must be an integer representing seconds past 01 Jan 1970 00:00:00 UTC, i.e. <a href="https://en.wikipedia.org/wiki/Unix_time">UNIX time</a>.</p>

<p>Providers <strong>SHALL</strong> reject requests with expired tokens.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"exp": 1469436987</code></p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> To ensure accuracy of timestamps, and minimise the likelihood of tokens being rejected due to clock skew providers and consumers <strong>SHALL</strong> synchronise their server clocks with NHS Network Time Protocol (NTP) servers.</div>

<hr />

<h4 id="iat-issued-at-claim"><code class="highlighter-rouge">iat</code> (issued at) claim</h4>

<p>The time the request and token were generated in UTC.</p>

<p>The value <strong>SHALL</strong> be an integer representing seconds past 01 Jan 1970 00:00:00 UTC, i.e. <a href="https://en.wikipedia.org/wiki/Unix_time">UNIX time</a>.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"iat": 1469436687</code></p>

<hr />

<h4 id="reason_for_request-claim"><code class="highlighter-rouge">reason_for_request</code> claim</h4>

<p>The purpose for which access is being requested.</p>

<p>GP Connect supports two reasons for requesting the patient record:</p>
<ul>
  <li><code class="highlighter-rouge">directcare</code> where the record is being requested to support direct care</li>
  <li><code class="highlighter-rouge">migration</code> where the record is being retrieved for the purpose of migration, for example, a GP2GP record transfer</li>
</ul>

<p><strong>Example</strong>: <code class="highlighter-rouge">"reason_for_request": "directcare"</code></p>

<hr />

<h4 id="requested_scope-claim"><code class="highlighter-rouge">requested_scope</code> claim</h4>

<p>The scope of the request.</p>

<p>Please see the table below for which values to populate.</p>

<table>
  <thead>
    <tr>
      <th>Claim value</th>
      <th>Description</th>
      <th>When to use</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">patient/*.read</code></td>
      <td>Patient record read request</td>
      <td>- <a href="foundations_use_case_find_a_patient.html">Find a patient</a><br /> - <a href="foundations_use_case_read_a_patient.html">Read a patient</a><br /> - <a href="appointments_use_case_retrieve_a_patients_appointments.html">Retrieve a patient’s appointments</a><br /> - <a href="appointments_use_case_read_an_appointment.html">Read an appointment</a><br /> - <a href="accessrecord_structured_development_retrieve_patient_record.html">Get patient’s structured record</a><br /> - <a href="accessrecord_structured_development_migrate_patient_record.html">Migrate patient’s structured record</a><br /> - <a href="access_documents_use_case_find_a_patient.html">Find a patient (Access Document)</a><br /> - <a href="access_documents_development_search_patient_documents.html">Search for a patient’s documents</a><br /> - <a href="access_documents_development_retrieve_patient_documents.html">Retrieve a patient’s documents</a><br /></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">patient/*.write</code></td>
      <td>Patient record write request</td>
      <td>- <a href="foundations_use_case_register_a_patient.html">Register a patient</a><br />- <a href="appointments_use_case_book_an_appointment.html">Book an appointment</a><br />- <a href="appointments_use_case_amend_an_appointment.html">Amend an appointment</a><br />- <a href="appointments_use_case_cancel_an_appointment.html">Cancel an appointment</a><br /></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">organization/*.read</code></td>
      <td>Other read request</td>
      <td>- <a href="foundations_use_case_get_the_fhir_capability_statement.html">Get the capability statement</a><br />- <a href="foundations_use_case_find_a_practitioner.html">Find a practitioner</a><br />- <a href="foundations_use_case_read_a_practitioner.html">Read practitioner</a><br />- <a href="foundations_use_case_find_an_organisation.html">Find an organisation</a><br />- <a href="foundations_use_case_read_an_organisation.html">Read organisation</a><br />- <a href="foundations_use_case_read_a_location.html">Read location</a><br />- <a href="appointments_use_case_search_for_free_slots.html">Search for free slots</a><br />- <a href="accessrecord_structured_get_the_fhir_capability_statement.html">Get the capability statement (Access Record Structured)</a><br /></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">organization/*.write</code></td>
      <td>Other write request</td>
      <td><em>(none currently)</em></td>
    </tr>
  </tbody>
</table>

<p>In addition to the above values, the table below contains claims around the sensitivity/confidentiality of the requested information.</p>

<table>
  <thead>
    <tr>
      <th>Claim value</th>
      <th>Description</th>
      <th>When to use</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>conf/N</td>
      <td>Normal confidentiality</td>
      <td>- <a href="accessrecord_structured_development_retrieve_patient_record.html">Get patient’s structured record</a><br /> - <a href="accessrecord_structured_development_migrate_patient_record.html">Migrate patient’s structured record</a><br /> - <a href="access_documents_development_search_patient_documents.html">Search for a patient’s documents</a><br /> - <a href="access_documents_development_retrieve_patient_documents.html">Retrieve a patient’s documents</a><br /></td>
    </tr>
    <tr>
      <td>conf/R</td>
      <td>Restricted confidentiality</td>
      <td>Restricted confidentiality	This MUST be only be used in a restricted set of use cases, this is currently restricted to GP2GP record transfers. In this scenario, provider systems will check whether the requesting organisation is permitted to retrieve sensitive information from the patient’s record. <br /> - <a href="accessrecord_structured_development_retrieve_patient_record.html">Get patient’s structured record</a><br /> - <a href="accessrecord_structured_development_migrate_patient_record.html">Migrate patient’s structured record</a><br /> - <a href="access_documents_development_search_patient_documents.html">Search for a patient’s documents</a><br /> - <a href="access_documents_development_retrieve_patient_documents.html">Retrieve a patient’s documents</a><br /></td>
    </tr>
  </tbody>
</table>

<p>Where multiple values are required, they <strong>MUST</strong> be provided as a space separated string. Where no confidentiality scope has been included, provider systems <strong>MUST</strong> interpret this as normal confidentiality, <code class="highlighter-rouge">conf/N</code>.</p>

<p>Providers should also read the associated <a href="development_api_security_guidance.html#authorisation-of-access-to-endpoints">Security guidance</a> in relation to this claim.</p>

<p><strong>Example</strong>: <code class="highlighter-rouge">"requested_scope": "patient/*.read conf/N"</code></p>

<hr />

<h4 id="requesting_device-claim"><code class="highlighter-rouge">requesting_device</code> claim</h4>

<p>The system or device making the request, populated as a minimal <a href="https://www.hl7.org/fhir/STU3/device.html">Device</a> resource.</p>

<p>The consumer <strong>SHALL</strong> populate the following <a href="https://www.hl7.org/fhir/STU3/device.html">Device</a> fields:</p>

<ul>
  <li>an <code class="highlighter-rouge">identifier</code> element, with:
    <ul>
      <li><code class="highlighter-rouge">system</code> containing a consumer-defined system URL representing the type of identifier in the value field, e.g. <code class="highlighter-rouge">https://consumersupplier.com/Id/device-identifier</code></li>
      <li><code class="highlighter-rouge">value</code> containing the device or system identifier</li>
    </ul>
  </li>
  <li><code class="highlighter-rouge">model</code> with the consumer product or system name</li>
  <li><code class="highlighter-rouge">version</code> with the version number of the consumer product or system</li>
</ul>

<p>The <a href="https://www.hl7.org/fhir/STU3/device.html">Device</a> resource populated in this claim is a minimally populated resource to convey key details for audit, conforming to the base STU3 FHIR resources definition, and is not required to conform to a GP Connect FHIR resource profile.</p>

<p><strong>Example</strong>:</p>

<pre class="remove-highlight"><code class="no-highlight">"requesting_device": {
  "resourceType": "Device",
  "identifier": [
    {
      "system": "https://consumersupplier.com/Id/device-identifier",
      "value": "CONS-APP-4"
    }
  ],
  "model": "Consumer product name",
  "version": "5.3.0"
}
</code></pre>

<hr />

<h4 id="requesting_organization-claim"><code class="highlighter-rouge">requesting_organization</code> claim</h4>

<p>The consumer organisation making the request, populated as a minimal <a href="https://www.hl7.org/fhir/STU3/organization.html">Organization</a> resource.</p>

<p>The consumer <strong>SHALL</strong> populate the following <a href="https://www.hl7.org/fhir/STU3/organization.html">Organization</a> fields:</p>

<ul>
  <li><code class="highlighter-rouge">name</code> with the name of the organisation</li>
  <li>an <code class="highlighter-rouge">identifier</code> element, with:
    <ul>
      <li><code class="highlighter-rouge">system</code> containing <code class="highlighter-rouge">https://fhir.nhs.uk/Id/ods-organization-code</code>, and</li>
      <li><code class="highlighter-rouge">value</code> containing the ODS code of the organisation</li>
    </ul>
  </li>
</ul>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> In consumer system topologies where GP Connect consumer applications are provisioned via a portal or middleware hosted by another organisation, it is vital for audit purposes that the organisation populated in the JWT reflects the organisation from where the request originates, rather than the hosting organisation.<br />
This is normally determined as the organisation of the logged on user making the request.</div>

<p>The <a href="https://www.hl7.org/fhir/STU3/organization.html">Organization</a> resource populated in this claim is a minimally populated resource to convey key details for audit, conforming to the base STU3 FHIR resources definition, and is not required to conform to a GP Connect FHIR resource profile.</p>

<p><strong>Example</strong>:</p>

<pre class="remove-highlight"><code class="no-highlight">"requesting_organization": {
  "resourceType": "Organization",
  "identifier": [
    {
      "system": "https://fhir.nhs.uk/Id/ods-organization-code",
      "value": "A1001"
    }
  ],
  "name": "Test Hospital"
}
</code></pre>

<hr />

<h4 id="requesting_practitioner-claim"><code class="highlighter-rouge">requesting_practitioner</code> claim</h4>

<p>The user making the request, populated as a minimal <a href="https://www.hl7.org/fhir/STU3/practitioner.html">Practitioner</a> resource.</p>

<p>To contain the logged on user’s identifier(s) (for example, login details / username). Where the user has both a local system user role as well as a nationally-recognised user role, then both <strong>SHALL</strong> be provided.</p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> This field <strong>SHALL NOT</strong> be populated with fixed values or a generic “system” user. The values <strong>SHALL</strong> represent the logged on user making the request.</div>

<p>The consumer <strong>SHALL</strong> populate the following <a href="https://www.hl7.org/fhir/STU3/practitioner.html">Practitioner</a> fields. The only exception to this is for the <a href="accessrecord_structured_development_migrate_patient_record.html">Migrate patient’s structured record</a> interaction where the fields <strong>SHOULD</strong> be populated:</p>

<ul>
  <li><code class="highlighter-rouge">id</code> with a unique <a href="https://www.hl7.org/fhir/STU3/resource.html#id">logical</a> identifier (e.g. user ID or GUID) for the logged on user. This <strong>SHALL</strong> match the value of the <a href="integration_cross_organisation_audit_and_provenance.html#sub-subject-claim"><code class="highlighter-rouge">sub</code> (subject) claim</a>.</li>
  <li><code class="highlighter-rouge">name</code> with:
    <ul>
      <li><code class="highlighter-rouge">family</code> containing the user’s family name</li>
      <li><code class="highlighter-rouge">given</code> containing the user’s given name</li>
      <li><code class="highlighter-rouge">prefix</code> containing the user’s title, where available</li>
    </ul>
  </li>
  <li>an <code class="highlighter-rouge">identifier</code> element with:
    <ul>
      <li><code class="highlighter-rouge">system</code> containing <code class="highlighter-rouge">https://fhir.nhs.uk/Id/sds-user-id</code></li>
      <li><code class="highlighter-rouge">value</code> containing the SDS user ID from the user’s NHS smartcard, or the value <code class="highlighter-rouge">UNK</code> if the user is not logged on with an NHS smartcard</li>
    </ul>
  </li>
  <li>an <code class="highlighter-rouge">identifier</code> element with:
    <ul>
      <li><code class="highlighter-rouge">system</code> containing <code class="highlighter-rouge">https://fhir.nhs.uk/Id/sds-role-profile-id</code></li>
      <li><code class="highlighter-rouge">value</code> containing the SDS user role profile ID from the user’s NHS smartcard, or the value <code class="highlighter-rouge">UNK</code> if the user is not logged on with an NHS smartcard</li>
    </ul>
  </li>
  <li>an <code class="highlighter-rouge">identifier</code> element containing a unique local user or user-role identifier for the logged on user (e.g. user ID, user role ID, logon name) from the consumer system:
    <ul>
      <li><code class="highlighter-rouge">system</code> containing a consumer-defined system URL representing the type of identifier in the value field, e.g. <code class="highlighter-rouge">https://consumersupplier.com/Id/user-guid</code></li>
      <li><code class="highlighter-rouge">value</code> containing the unique local identifier for the logged on user</li>
    </ul>
  </li>
</ul>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> Providers should be aware of variance in the population of the <code class="highlighter-rouge">identifier</code> field amongst existing consumer systems when reading this claim, specifically the latter two elements (SDS role profile ID, and local user identifier) are not always present.</div>

<p>The <a href="https://www.hl7.org/fhir/STU3/practitioner.html">Practitioner</a> resource populated in this claim is a minimally populated resource to convey key details for audit, conforming to the base STU3 FHIR resources definition, and is not required to conform to a GP Connect FHIR resource profile.</p>

<p><strong>Example</strong>:</p>

<pre class="remove-highlight"><code class="no-highlight">"requesting_practitioner": {
  "resourceType": "Practitioner",
  "id": "10019",
  "identifier": [
    {
      "system": "https://fhir.nhs.uk/Id/sds-user-id",
      "value": "111222333444"
    },
    {
      "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
      "value": "444555666777"
    },
    {
      "system": "https://consumersupplier.com/Id/user-guid",
      "value": "98ed4f78-814d-4266-8d5b-cde742f3093c"
    }
  ],
  "name": [
    {
      "family": "Jones",
      "given": [
        "Claire"
      ],
      "prefix": [
        "Dr"
      ]
    }
  ]
}</code></pre>

<h3 id="jwt-payload-full-example">JWT payload full example</h3>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"iss"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://consumersupplier.thirdparty.nhs.uk/"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"sub"</span><span class="p">:</span><span class="w"> </span><span class="s2">"10019"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"aud"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://providersupplier.thirdparty.nhs.uk/GP0001/STU3/1"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"exp"</span><span class="p">:</span><span class="w"> </span><span class="mi">1469436987</span><span class="p">,</span><span class="w">
  </span><span class="s2">"iat"</span><span class="p">:</span><span class="w"> </span><span class="mi">1469436687</span><span class="p">,</span><span class="w">
  </span><span class="s2">"reason_for_request"</span><span class="p">:</span><span class="w"> </span><span class="s2">"directcare"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"requested_scope"</span><span class="p">:</span><span class="w"> </span><span class="s2">"patient/*.read"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"requesting_device"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Device"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://consumersupplier.com/Id/device-identifier"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"CONS-APP-4"</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">],</span><span class="w">
    </span><span class="s2">"model"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Consumer product name"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"version"</span><span class="p">:</span><span class="w"> </span><span class="s2">"5.3.0"</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"requesting_organization"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Organization"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/Id/ods-organization-code"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"A1001"</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">],</span><span class="w">
    </span><span class="s2">"name"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Test Hospital"</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"requesting_practitioner"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Practitioner"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"10019"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/Id/sds-user-id"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"111222333444"</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/Id/sds-role-profile-id"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"444555666777"</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://consumersupplier.com/Id/user-guid"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"98ed4f78-814d-4266-8d5b-cde742f3093c"</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">],</span><span class="w">
    </span><span class="s2">"name"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="p">{</span><span class="w">
        </span><span class="s2">"family"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Jones"</span><span class="p">,</span><span class="w">
        </span><span class="s2">"given"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="s2">"Claire"</span><span class="w">
        </span><span class="p">],</span><span class="w">
        </span><span class="s2">"prefix"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="s2">"Dr"</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">}</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h2 id="external-documentspolicy-documents">External documents/policy documents</h2>

<table>
  <tbody>
    <tr>
      <td>Name</td>
      <td>Author</td>
      <td>Version</td>
      <td>Updated</td>
    </tr>
    <tr>
      <td>GPSoC IG Requirements for GP Systems</td>
      <td>NHS Digital</td>
      <td>v4.0</td>
      <td>19/09/2014</td>
    </tr>
    <tr>
      <td>GP Systems Interface Mechanism Requirements V 1</td>
      <td>NHS Digital</td>
      <td>v0.10</td>
      <td> </td>
    </tr>
  </tbody>
</table>




    

</div>

 </div>





</div>
 <!-- /.row -->
</div>
<!-- /.container -->
    </div>

<!-- END FROM GITHUB TEMPLATE -->
<!--end apicontent--></div></div></div>
</div><!--end main_content-->
</div><!-- end main -->
