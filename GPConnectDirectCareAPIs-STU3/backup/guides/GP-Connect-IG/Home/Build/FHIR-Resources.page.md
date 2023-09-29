<div class="post-header">
   <h1 class="post-title-main">FHIR&reg; resources</h1>
</div>





<div class="post-content">

   
<div class="summary"><b>Summary:</b> Where to find details of what resources and operations a FHIR server should expose to be a fully compliant GP Connect solution</div>

 <h2 id="introduction">Introduction</h2>

<p>GP Connect versions 1.x use the <a href="http://hl7.org/fhir/STU3/">FHIR STU3</a> standard to specify the API and profiles.</p>

<h2 id="profiling-principles">Profiling principles</h2>

<blockquote>
  <p>Please see the <a href="designprinciples_data_model_principles.html">Data model principles</a> page for further information.</p>
</blockquote>

<h2 id="profiles-for-each-capability-pack">Profiles for each capability pack</h2>

<p>The profiled FHIR resources required for each of the GP Connect capability packs are specified within the specific specification sections for each of the capabilities:</p>

<ul>
  <li><a href="datalibraryfoundation.html">Foundations</a></li>
  <li><a href="accessrecord.html">Access Record HTML</a></li>
  <li><a href="accessrecord_structured_development_resources_overview.html">Access Record Structured</a></li>
  <li><a href="datalibraryappointment.html">Appointment Management</a></li>
  <li><a href="access_documents_development_resources_overview.html">Access Document</a></li>
</ul>

<h2 id="general-fhir-resource-population-requirements">General FHIR resource population requirements</h2>

<h3 id="population-of-optional-elements">Population of optional elements</h3>

<p>The purpose of GP Connect is to make the patient data stored within the GP systems available externally so that it can be used to help improve the quality of patient care across the NHS. To give patients the best care possible the data made available through the GP Connect API should be as complete as possible. Therefore, it is expected that both provider and consumers:</p>

<ul>
  <li><strong><em>SHALL</em></strong> populate all the elements within FHIR resources subject to any Capability-specific variance, where data is available within their system irrespective of the cardinality of the elements within the FHIR resource profiles.</li>
</ul>

<p>As GP Connect has made the FHIR resources open to aid in interoperability this means that there are some elements included in FHIR profiles which are not applicable to our deployment settings, for example ‘specialism’ in the appointment resource. For these elements if the provider or consumer does not have data stored within their system the element will not be populated.</p>

<h3 id="use-of-must-support-flag">Use of Must-Support flag</h3>

<p>Some resource profiles used in GP Connect make use of the <a href="https://www.hl7.org/fhir/STU3/conformance-rules.html#mustSupport">Must-Support</a> flag.</p>

<p>Where a Must-Support flag is present on a resource element, a <code class="highlighter-rouge">consumer</code> system SHALL populate the field in the request body if data is available to do so, irrespective of the fact that field cardinality may be <code class="highlighter-rouge">0..1</code> or <code class="highlighter-rouge">0..*</code>.</p>

<p>Similarly, <code class="highlighter-rouge">provider</code> systems SHALL populate an element in responses where data is available to do so, irrespective of optional cardinality. When a <code class="highlighter-rouge">provider</code> system receives data from a consumer for a field marked with the Must-Support flag, the provider system SHALL store this data field in such a way that the data element is preserved and the element can be populated in future responses to consumer requests for the resource in question.</p>

<p>If an element within a FHIR profile is marked as must support then all sub elements of that element SHALL also be considered must support. For example, within the GP Connect Appointment profile the booking organization extension is flagged with must support on the extension. This means that the extension and all sub elements within the extension are must support and SHALL be stored in a way that the data is preserved and the booking organization can be populated in future responses to consumers requesting that resource.</p>

<p>For example, see the <a href="foundations_use_case_register_a_patient.html#payload-request-body">Register a patient request body</a>.</p>

<h2 id="fhir-resource-elementdata-type-specific-population-requirements">FHIR resource element/data type specific population requirements</h2>

<h3 id="id">id</h3>

<p>The logical id of all FHIR resources SHALL be populated in accordance with the <a href="https://www.hl7.org/fhir/STU3/resource.html#id">FHIR specification requirements</a>, meaning that population of the element is expected.</p>

<h3 id="address">Address</h3>

<p>The <code class="highlighter-rouge">Address</code> data type is used in many of the FHIR resources across the GP Connect API. Where an element using the <code class="highlighter-rouge">Address</code> data type is present in a FHIR resource the following population guidance SHALL be followed:</p>

<ul>
  <li>The address SHALL be populated using the elements:
    <ul>
      <li><code class="highlighter-rouge">line</code>
        <ul>
          <li>E.g. House name, flat number, house number and street &amp; village or locality.  Multiple <code class="highlighter-rouge">line</code> elements SHALL be populated, where more than one line is present.</li>
        </ul>
      </li>
      <li><code class="highlighter-rouge">city</code></li>
      <li><code class="highlighter-rouge">district</code>
        <ul>
          <li>This element is to carry county, where present.</li>
        </ul>
      </li>
      <li><code class="highlighter-rouge">postalCode</code></li>
      <li><code class="highlighter-rouge">country</code></li>
    </ul>
  </li>
  <li>
    <p>Where an element is not present, the element SHALL NOT be populated.</p>
  </li>
  <li>
    <p>The <code class="highlighter-rouge">text</code> element SHOULD NOT be populated within the address.</p>
  </li>
  <li><code class="highlighter-rouge">use</code> SHALL be populated for patient or patient contact addresses and SHOULD be populated in other contexts.</li>
</ul>

<p>Example:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{
  "use": "home",
  "line": [
    "Trevelyan Square",
    "Boar Ln"
  ],
  "city": "Leeds",
  "district": "West Yorkshire",
  "postalCode": "LS1 6AE"
}
</code></pre></div></div>

<h3 id="contactpoint">ContactPoint</h3>

<p>The <code class="highlighter-rouge">ContactPoint</code> data type is used in many of the FHIR resources across the GP Connect API. Where an element using the <code class="highlighter-rouge">ContactPoint</code> data type is present in a FHIR resource the following population guidance SHALL be followed:</p>

<ul>
  <li>The telecom number or address (telephone number, email address etc) SHALL be populated in the <code class="highlighter-rouge">value</code> element</li>
  <li><code class="highlighter-rouge">system</code> SHALL be populated in all circumstances</li>
  <li><code class="highlighter-rouge">use</code> SHALL be populated for patient or patient contact telecom details and SHOULD be populated in other contexts.</li>
</ul>

<p>Example:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{
  "system": "phone",
  "value": "01454587554",
  "use": "home"
}
</code></pre></div></div>

<h3 id="patientcontact">Patient.contact</h3>

<p>The Patient.contact element SHALL be populated where demographic information is available in the Patient record for those individuals who may need to be contacted in connection with the Patient’s appointment.  In accordance with the FHIR definition, it is “Not applicable to register pedigree and family ties beyond use of having contact”.</p>

<ul>
  <li><code class="highlighter-rouge">relationship.text</code> SHALL be populated with the type of relationship, for example <em>Emergency context</em>, <em>Next of kin</em>, or <em>Carer</em>.  The element SHALL also be used where a family relationship is recorded, for example <em>Daughter</em>.  Multiple relationship entries are allowed.</li>
  <li><code class="highlighter-rouge">relationship.coding</code> SHALL NOT be populated</li>
  <li><code class="highlighter-rouge">name</code>, <code class="highlighter-rouge">telecom</code>, <code class="highlighter-rouge">address</code>, <code class="highlighter-rouge">gender</code>, <code class="highlighter-rouge">organization</code> and <code class="highlighter-rouge">period</code> SHALL be populated where data is available</li>
  <li><code class="highlighter-rouge">address</code> and <code class="highlighter-rouge">telecom</code> SHALL follow the <a href="development_fhir_resource_guidance.html#address">Address</a> and <a href="development_fhir_resource_guidance.html#contactpoint">ContactPoint</a> rules above for population of these elements</li>
</ul>

<p>Example:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{
  "relationship": [
    {
      "text": "Emergency contact"
    },
    {
      "text": "Next of kin"
    },
    {
      "text": "Daughter"
    }
  ],
  "name": {
    "use": "official",
    "text": "JACKSON Jane (Miss)",
    "family": "Jackson",
    "given": [
      "Jane"
    ],
    "prefix": [
      "Miss"
    ]
  },
  "telecom": [
    {
      "system": "phone",
      "value": "07777123123",
      "use": "mobile"
    }
  ],
  "address": {
    "use": "home",
    "type": "physical",
    "line": [
      "Trevelyan Square",
      "Boar Ln"
    ],
    "city": "Leeds",
    "district": "West Yorkshire",
    "postalCode": "LS1 6AE"
  },
  "gender": "female"
}
</code></pre></div></div>

<h3 id="bundleentryfullurl">Bundle.entry.fullUrl</h3>

<p>Providers SHOULD NOT populate <code class="highlighter-rouge">Bundle.entry.fullUrl</code>.</p>

<p>Consumers MUST NOT use <code class="highlighter-rouge">Bundle.entry.fullUrl</code>.</p>




    

</div>





</div>
<!-- /.row -->
</div>
<!-- /.container -->
</div>   

   