## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">Branch surgeries</h1>
</div>





<div class="post-content">

   
<div class="summary"><b>Summary</b>Describes how GP Connect manages branch surgery data</div>
   

   

    
    
<!-- this handles the automatic toc. use ## for subheads to auto-generate the on-page minitoc. if you use html tags, you must supply an ID for the heading element in order for it to appear in the minitoc. -->

<div id="toc"></div>

    

  <h2 id="gp-practices-with-multiple-surgeries">GP practices with multiple surgeries</h2>

<p>A GP practice may operate from a single surgery (location) or from multiple surgeries (multiple locations).</p>

<p>In GP Connect, a GP practice is represented by an <code class="highlighter-rouge">Organization</code> resource, and the surgeries are represented by <code class="highlighter-rouge">Location</code> resources.  The surgery <code class="highlighter-rouge">Location</code> is linked to the GP practice <code class="highlighter-rouge">Organization</code> via the <code class="highlighter-rouge">Location.managingOrganisation</code> element.</p>


{{render:branch-surgeries.png}}
<p>A GP practice operating multiple surgeries usually designates one of the surgeries as a <em>main</em> surgery and the rest as <em>branch</em> surgeries. The designation of surgeries as <em>main</em> and <em>branch</em> doesn’t have significant impact on GP Connect other than the main surgery normally having the same name and address as the GP practice, and the branch surgeries having different names and addresses.</p>

<p>When a patient registers at a GP practice with multiple surgeries, they are assigned a ‘preferred’ surgery, even though the patient is formally registered to the GP practice (organisation) as a whole, and can usually attend appointments at any of the surgeries (locations).</p>

<h3 id="ods-codes">ODS codes</h3>

<p>In GP Connect, an ODS code identifies a GP practice as a whole, and is populated in the <code class="highlighter-rouge">Organization.identifier</code> element.</p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> While ODS <em>site</em> codes do exist to identify some branch surgeries, GP systems DO NOT use these and hence they are NOT available via the GP Connect interface, and cannot be used to route requests to individual surgeries.</div>

<h4 id="personal-demographics-service">Personal Demographics Service</h4>

<p>The <a href="integration_personal_demographic_service.html">Personal Demographics Service</a> is used by GP Connect consuming systems to verify a patient’s identity, and also to retrieve the ODS code of a patient’s registered GP practice.</p>

<p>The ODS code stored in a patient’s PDS record represents the GP practice as a whole, and does not identify the patient’s preferred surgery.</p>

<h4 id="gp-connect-routing">GP Connect routing</h4>

<p>GP Connect uses ODS codes in order to route requests to a GP practice by including the practice’s ODS code in the URL (see <a href="development_general_api_guidance.html#service-root-url">Service Root URL</a>).</p>

<p>Therefore, when a GP Connect request is sent, it is sent to a practice as a whole, and not to a specific surgery.</p>

<p>The following query to read a <code class="highlighter-rouge">Patient</code> resource is being sent to the patient’s GP practice identified by the ODS code <code class="highlighter-rouge">D82809</code>:</p>

<p><code class="highlighter-rouge">https://provider.nhs.uk/<b>D82809</b>/STU3/1/gpconnect/Patient/1</code></p>

<h3 id="implications-for-access-record-html-access-record-structured-and-access-document">Implications for Access Record HTML, Access Record Structured and Access Document</h3>

<p>There are no implications for Access Record HTML, Access Record Structured and Access Document because the patient’s record and documents are requested from the GP practice as a whole and not from an individual surgery.</p>

<h3 id="implications-for-appointment-management">Implications for Appointment Management</h3>

<p>Because a GP practice’s appointment book can hold appointments across multiple surgeries (locations), it is important to distinguish which surgery an appointment is held at, to allow the patient to decide where they wish to attend.</p>

<p>In order to do this, every <code class="highlighter-rouge">Schedule</code> resource has an associated <code class="highlighter-rouge">Location</code> resource which represents the surgery that the appointment will take place at, including the surgery’s name, address and contact details.</p>

<p>To retrieve the patient’s preferred surgery (assigned when they registered with the practice), a reference to the surgery <code class="highlighter-rouge">Location</code> is held in <code class="highlighter-rouge">Patient.registrationDetails.preferredBranchSurgery</code>.  This can be used to identify  appointment slots at the patient’s preferred surgery by comparing its logical id with that of the <code class="highlighter-rouge">Location</code> resource referenced from the <code class="highlighter-rouge">Schedule.actor</code> element.</p>




    

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