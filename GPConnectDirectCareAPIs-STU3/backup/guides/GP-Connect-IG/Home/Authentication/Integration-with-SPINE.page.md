## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">Spine integration illustrated</h1>
</div>


<div class="post-content">

   
<div class="summary">Illustration of the use of the GP Connect API showing all interactions required - both with Spine services and GP Connect endpoint API calls.</div>
    
    
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

    

  <h2 id="spine-integration-required-to-consume-gp-connect-capabilities">Spine integration required to consume GP Connect capabilities</h2>

<p>GP Connect provider APIs are accessed through the NHS Spine. As such, consumers of GP Connect APIs are required to integrate with the following Spine services as a prerequisite to making API calls to GP Connect provider APIs:</p>

- [Personal Demographics Service (PDS)]( https://developer.nhs.uk/apis/gpconnect-1-6-0/integration_personal_demographic_service.html)
- [Spine Directory Service (SDS)] (https://developer.nhs.uk/apis/gpconnect-1-6-0/integration_spine_directory_service.html)

- [Spine Secure Proxy (SSP)](https://developer.nhs.uk/apis/gpconnect-1-6-0/integration_spine_secure_proxy.html)

<h2 id="overview">Overview</h2>

{{render:gpconnect-flow.png}}


<p><strong>Step 1. Personal Demographics Service</strong></p>

<p>A GP Connect consumer queries PDS for the patient in order to:</p>

<ul>
  <li>Verify the patient’s NHS number</li>
  <li>Retrieve the ODS organisation code of the patient’s registered GP practice</li>
</ul>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> Appointment Management consumer suppliers may wish to build workflows that support appointment booking into other GP practices (other than the patient’s registered practice) such as into Extended Access Hubs. For these consumers, an alternate mechanism for discovering the target practice’s ODS organisation code is required. Please see the <a href="appointments_service_discovery.html">Appointment Management Service Discovery page</a> for more details.</div>

<p>For further details on this step please see the <a href="integration_personal_demographic_service.html">Personal Demographic Service</a> page.</p>

<p><strong>Step 2. Spine Directory Service</strong></p>

<p>A GP Connect consumer queries SDS using the ODS organisation code retrieved in the previous step in order to retrieve:</p>

<ul>
  <li>The GP practice’s GP Connect service root URL (their FHIR endpoint)</li>
  <li>The GP practice’s GP Connect ASID</li>
</ul>

<p>For further details on this step please see the <a href="integration_spine_directory_service.html">Spine Directory Services - overview and querying</a> page.</p>

<p><strong>Step 3 onwards. Spine Secure Proxy</strong></p>

<p>A GP Connect consumer constructs a GP Connect FHIR request (incorporating the two items retrieved in the previous step), and sends it to the SSP.</p>

<p>The SSP then forwards the request on to the GP Connect provider system which returns its response back through to the SSP to the consumer system.  A number of GP Connect FHIR requests may be made in order to satisfy the full workflow of the capability.</p>

<p>For further details on this step please see the <a href="integration_spine_secure_proxy.html">Spine Secure Proxy</a> page.</p>

<p>Please see the full worked example below for the steps required to consume the GP Connect Appointment Management capability.</p>

<h2 id="worked-example-integrate-with-spine-to-book-an-appointment-at-the-patients-registered-gp-practice">Worked example: Integrate with Spine to book an appointment at the patient’s registered GP practice</h2>

<p>The following sequence diagram illustrates the steps which a GP Connect consumer would be required to undertake in order to book an appointment at the patient’s registered GP practice.</p>

{{render:integration_sequence_diagram.png}}


<p>The steps shown in the diagram are detailed below.</p>

<table>
  <thead>
    <tr>
      <th>Step</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> </td>
      <td><em>Step 1 is optional in the sense that a cached version of a these trace results may be available to the consumer.</em></td>
    </tr>
    <tr>
      <td>1a</td>
      <td><strong>Consumer</strong> is responsible for performing a  <a href="integration_personal_demographic_service.html">Personal Demographics Service(PDS)</a> Trace to both verify the NHS Number and obtain the ODS code of the GP Practice system.</td>
    </tr>
    <tr>
      <td>1b</td>
      <td><strong>PDS</strong> returns NHS Number verification status, and the ODS code of the patient’s registered GP practice.</td>
    </tr>
    <tr>
      <td>Note:</td>
      <td><em>Appointment Management consumers that wish to book into other GP practices require <a href="appointments_service_discovery.html">an alternate mechanism</a> for determining a GP practice ODS code. Regardless of the mechanism used to determine a GP practices ODS code, the PDS step is required in order to verify the patient’s NHS number.</em></td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td><em>Step 2 is optional in the sense that cached or configured endpoint details for the Practice may be available from a previous SDS interaction.</em></td>
    </tr>
    <tr>
      <td>2a</td>
      <td><strong>Consumer</strong> calls Spine Directory Service again to discover the URL of the FHIR server endpoint at the practice</td>
    </tr>
    <tr>
      <td>2b</td>
      <td><strong>SDS</strong> returns details of the FHIR endpoint.</td>
    </tr>
    <tr>
      <td>2c</td>
      <td><strong>Consumer</strong> calls <a href="integration_spine_directory_service.html">Spine Directory Service (SDS)</a> to discover the Accredited System ID (ASID) of the system which provides a FHIR endpoint at the practice identified by the specified ODS code.</td>
    </tr>
    <tr>
      <td>2d</td>
      <td><strong>SDS</strong> returns the ASID.</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td><em>Step 3 is optional in the sense that the Capability Statement may be used to verify the FHIR capabilities which the endpoint provides should this be required at run time. The results of this call may be cached for future interactions.</em></td>
    </tr>
    <tr>
      <td>3a</td>
      <td><strong>Consumer</strong> calls the <a href="foundations_use_case_get_the_fhir_capability_statement.html">metadata endpoint</a> at the practice FHIR server to request full details of which FHIR operations are implemented at that server - the Capability Statement.</td>
    </tr>
    <tr>
      <td>3b</td>
      <td><strong>Spine Secure Proxy (SSP)</strong> receives the call from the Consumer, performs security checks, and if these pass, forwards the consumer request to the provider.</td>
    </tr>
    <tr>
      <td>3c</td>
      <td><strong>Provider</strong> returns the Capability Statement to the SSP.</td>
    </tr>
    <tr>
      <td>3d</td>
      <td><strong>SSP</strong> forwards the Capability Statement received from the Provider to the Consumer.</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>4a</td>
      <td><strong>Consumer</strong> then makes an API call to <a href="appointments_use_case_search_for_free_slots.html">Search for free slots</a> at the practice in the specified time-frame.</td>
    </tr>
    <tr>
      <td>4b</td>
      <td><strong>SSP</strong> forwards the call from the Consumer, performs security checks, and if these pass, forwards the consumer request to the provider.</td>
    </tr>
    <tr>
      <td>4c</td>
      <td><strong>Provider</strong> responds with details of what slots are available for booking. Should no applicable slots be returned, the consumer may make repeated calls to <a href="appointments_use_case_search_for_free_slots.html">Search for free slots</a> with amended date ranges.</td>
    </tr>
    <tr>
      <td>4d</td>
      <td><strong>SSP</strong> forwards the free slots received from the Provider to the Consumer.</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>5a</td>
      <td><strong>Consumer</strong> makes API call to <a href="foundations_use_case_find_a_patient.html">Find a patient</a> providing the patient’s NHS Number.</td>
    </tr>
    <tr>
      <td>5b</td>
      <td><strong>Spine Secure Proxy (SSP)</strong> receives the call from the Consumer, performs security checks, and if these pass, forwards the consumer request to the provider.</td>
    </tr>
    <tr>
      <td>5c</td>
      <td><strong>Provider</strong> finds patient record and returns the logical identifier of the patient record at this practice in their system. See <a href="appointments_consumer_sessions.html#consumer-session---booking-an-appointment---no-patient-record">Patient record not present</a> for an illustration of the steps required in this case.</td>
    </tr>
    <tr>
      <td>5d</td>
      <td><strong>SSP</strong> forwards the Patient details received from the Provider to the Consumer</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>6a</td>
      <td><strong>Consumer</strong> calls <a href="appointments_use_case_book_an_appointment.html">Book an appointment</a> indicating the slots selected in the UI together with the logical ID of the patient.</td>
    </tr>
    <tr>
      <td>6b</td>
      <td><strong>Spine Secure Proxy (SSP)</strong> forwards the call from the Consumer, performs security checks, and if these pass, forwards the consumer request to the provider.</td>
    </tr>
    <tr>
      <td>6c</td>
      <td><strong>Provider</strong> responds with details of the booked appointment as confirmation of success.</td>
    </tr>
    <tr>
      <td>6d</td>
      <td><strong>SSP</strong> forwards the Appointment details received from the Provider to the Consumer.</td>
    </tr>
  </tbody>
</table>




    

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
