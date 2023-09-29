## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">FHIR&reg; implementation</h1>
</div>

<div class="post-content">

   
<div class="summary">Implementation guidance for developers - focusing on FHIR&reg; specifics</div>
<p>To help API implementers deal with the FHIR learning curve, NHS Digital has worked to constrain the scope of the FHIR® standard that is expected to be implemented in the first tranche of development work as follows:</p>

<ol>
  <li><a href="https://www.hl7.org/fhir/STU3/resource.html">Resource</a>
    <ol>
      <li><a href="https://www.hl7.org/fhir/STU3/resource.html#id">Resource identity</a></li>
      <li><a href="https://www.hl7.org/fhir/STU3/resource.html#identifiers">Business identifiers</a></li>
    </ol>
  </li>
  <li><a href="https://www.hl7.org/fhir/STU3/domainresource.html">Domain resource</a>
    <ol>
      <li>Common API
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/patient.html">Patient</a> profiled as gpconnect-patient-1.</li>
          <li><a href="https://www.hl7.org/fhir/STU3/practitioner.html">Practitioner</a> profiled as gpconnect-practitioner-1.</li>
          <li><a href="https://www.hl7.org/fhir/STU3/organization.html">Organisation</a> profiled as gpconnect-organization-1.</li>
          <li><a href="https://www.hl7.org/fhir/STU3/location.html">Location</a> profiled as gpconnect-location-1</li>
        </ol>
      </li>
      <li>Care record API
        <ol>
          <li>Please refer to the <a href="#ResourceDataType">Resource data types</a> section of this page.</li>
        </ol>
      </li>
      <li>Bookings API
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/schedule.html">Schedule</a> profiled as gpconnect-schedule-1</li>
          <li><a href="https://www.hl7.org/fhir/STU3/slot.html">Slot</a> profiled as gpconnect-slot-1</li>
          <li><a href="https://www.hl7.org/fhir/STU3/appointment.html">Appointment</a> profiled as gpconnect-appointment-1</li>
        </ol>
      </li>
    </ol>
  </li>
  <li><a href="https://www.hl7.org/fhir/STU3/resource.html#Meta">Resource metadata</a>
    <ol>
      <li><a href="https://www.hl7.org/fhir/STU3/resource.html#metadata">Profile</a></li>
      <li><a href="https://www.hl7.org/fhir/STU3/resource.html#metadata">Version Id</a></li>
    </ol>
  </li>
  <li><a href="https://www.hl7.org/fhir/STU3/bundle.html">Bundle</a></li>
  <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html">Data types</a>
    <ol>
      <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#primitive">Primitive types</a>
        <ol>
          <li>All primitive types SHALL be supported.</li>
        </ol>
      </li>
      <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#complex">Complex types</a>
        <ol>
          <li>The following complex types SHALL be supported.
            <ol>
              <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#identifier">Identifier</a></li>
              <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#codeableconcept">Coding</a></li>
              <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#coding">Codeable Concept</a></li>
              <li><a href="https://www.hl7.org/fhir/STU3/datatypes.html#period">Period</a></li>
            </ol>
          </li>
          <li>It is expected that further complex types will be introduced as required to model structured data.</li>
        </ol>
      </li>
    </ol>
  </li>
  <li>Interactions
    <ol>
      <li>Instance
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#read">READ</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#update">UPDATE</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#delete">DELETE</a></li>
        </ol>
      </li>
      <li>Type level
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#create">CREATE</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#search">SEARCH</a></li>
        </ol>
      </li>
    </ol>
  </li>
  <li><a href="https://www.hl7.org/fhir/STU3/http.html#search">Search</a>
    <ol>
      <li><a href="https://www.hl7.org/fhir/STU3/search.html#ptypes">Search parameter types</a>
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#date">Date</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#token">Token</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#reference">Reference</a></li>
        </ol>
      </li>
      <li><a href="https://www.hl7.org/fhir/STU3/search.html#prefix">Search prefixes</a>
        <ol>
          <li>lt (less than)</li>
          <li>le (less or equal to)</li>
          <li>gt (great than)</li>
          <li>ge (greater or equal to)</li>
          <li>eq (equal to)</li>
        </ol>
      </li>
      <li>Parameters for all resources
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#query">_query</a></li>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#list">_list</a></li>
        </ol>
      </li>
      <li>Search result parameters
        <ol>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#include">_include</a> can be used internally inside a named <code class="highlighter-rouge">_query</code> operation.</li>
          <li><a href="https://www.hl7.org/fhir/STU3/search.html#sort">_sort</a> can be used internally inside a named <code class="highlighter-rouge">_query</code> operation.</li>
        </ol>
      </li>
    </ol>
  </li>
  <li><a href="https://www.hl7.org/fhir/STU3/operations.html">Operations</a>
    <ol>
      <li><a href="https://www.hl7.org/fhir/STU3/operations.html#extensibility">Implementation defined operations</a></li>
    </ol>
  </li>
</ol>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> It is fully expected that over time new areas of the FHIR® standard will be brought into scope as new capabilities are requested and vendors’ understanding of FHIR® standard matures. This is in line with the agreed iterative/Agile engagement process that has been agreed between the NHS Digital and the principal GP system vendors.</div>

<h3 id="fhir-out-of-scope">FHIR out of scope</h3>

<p>GP Connect provider systems are not expected to implement the following aspects of the FHIR® standard under the scope of the first tranche of development work:</p>

<ol>
  <li>Operations
    <ol>
      <li>Validate a resource</li>
      <li>Meta operations</li>
      <li>Generate a document</li>
      <li>Process message</li>
      <li>Find a functional list</li>
      <li>ConceptMap operations</li>
      <li>Closure table maintenance</li>
      <li>Fetch records</li>
      <li>Questionnaire operations</li>
      <li>Terminology operations</li>
    </ol>
  </li>
  <li>Interactions
    <ol>
      <li>Instance
        <ol>
          <li>HISTORY</li>
          <li><a href="https://www.hl7.org/fhir/STU3/http.html#vread">VREAD</a></li>
        </ol>
      </li>
      <li>Type level
        <ol>
          <li>HISTORY</li>
        </ol>
      </li>
      <li>Whole system
        <ol>
          <li>BATCH TRANSACTION</li>
          <li>HISTORY</li>
          <li>SEARCH</li>
        </ol>
      </li>
      <li>Conditional interactions
        <ol>
          <li>CREATE</li>
          <li>UPDATE</li>
          <li>DELETE</li>
        </ol>
      </li>
    </ol>
  </li>
  <li>Search
    <ol>
      <li>Parameter types
        <ol>
          <li>Number</li>
          <li>String</li>
          <li>Quantity</li>
          <li>Composite</li>
          <li>URL</li>
        </ol>
      </li>
      <li>Parameters for all resources
        <ol>
          <li>_language</li>
          <li>_lastUpdate</li>
          <li>_tag</li>
          <li>_profile</li>
          <li>_security</li>
          <li>_text</li>
          <li>_content</li>
          <li>_filter</li>
        </ol>
      </li>
      <li>Search result parameters
        <ol>
          <li>_count</li>
          <li>_summary</li>
          <li>_elements</li>
          <li>_contained</li>
          <li>_containedType</li>
        </ol>
      </li>
      <li>Chained parameters</li>
      <li>Paging / Page count</li>
    </ol>
  </li>
  <li>Resource metadata
    <ol>
      <li>lastUpdated</li>
      <li>security</li>
      <li>tag</li>
    </ol>
  </li>
</ol>

<div class="alert alert-danger" role="alert"><i class="fa fa-exclamation-circle"></i> <b>Warning:</b> Providers are free to implement additional FHIR functionality above that mandated under the GP Connect delivery if they so desire. However, the Spine Secure Proxy (SSP) will only forward accredited system interactions.</div>

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> Providers MAY populate meta.lastUpdated (unless stated otherwise in a profile’s population guidance) if they hold an accurate date/time associated with the data items making up the profile. Consumers MUST NOT rely on this value being populated.</div>

<h3 id="fhir-system-conformance">FHIR system conformance</h3>

<p>Provider systems SHALL provide read-only <a href="https://www.hl7.org/fhir/STU3/capabilitystatement.html">FHIR CapabilityStatement resources</a> that identify all the profiles and operations that each FHIR server supports for each resource type.</p>

<p>A FHIR server’s capability statement SHALL be available using the following <a href="http://hl7.org/fhir/STU3/http.html#capabilities">capabilities interactions</a>:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>GET [base]/metadata {?_format=[mime-type]}
</code></pre></div></div>

<p>Please note:  The <code class="highlighter-rouge">[base]</code> portion may vary based on the GP Connect capability.</p>

<p>Refer to:</p>
<ul>
  <li><a href="foundations_use_case_get_the_fhir_capability_statement.html">Get the FHIR capability statement (Foundations)</a> for the capability statement describing the Foundations and Appointment Management capabilities</li>
  <li><a href="accessrecord_structured_get_the_fhir_capability_statement.html">Get the FHIR capability statement (Access Record Structured)</a> for the capability statement describing the Access Record Structured capability</li>
</ul>

<h3 id="fhir-resource-conformance">FHIR resource conformance</h3>

<p>To help a consumer find the correct set of reports for a use-case, a provider of resources SHALL, for any profile declared in <a href="https://www.hl7.org/fhir/STU3/profiling.html#2.13.0.3.2">CapabilityStatement.profile</a>, mark resources with profile assertions documenting the profile(s) they conform to. A provider of resources SHOULD also ensure that any resource instance that would reasonably be expected to conform to the declared profiles SHOULD be published in this form.</p>

<h3 id="gp-connect-fhir-api-conformance">GP Connect FHIR API conformance</h3>

<p>GP Connect comprises a number of RESTful API bundles. Each API bundle is intended to support sets of related use cases, for example the Appointment API bundle supports viewing, booking and cancelling GP appointments in a number of scenarios.</p>

<p>Individual API bundles may be provided independently of each other. GP Connect conformance may be claimed in relation to one or more API bundles. A provider claiming to provide an API bundle must be fully conformant (that is, implement all the resource profiles and interactions for the API bundle as specified in this document and all the general requirements described herein).</p>

<h3 id="incomplete-data---expected-behaviour">Incomplete data - expected behaviour</h3>

<p>Where resource instance data available in clinical systems is either insufficient or corrupt and thus a resource cannot be constructed by a provider system which meets the associated FHIR profile, the following guidance describes expected behaviour:</p>

<p><strong>Scenario: GET resource by logical ID</strong></p>

<p>An HTTP 500 error should be returned with an OperationOutcome resource providing diagnostic details. This may include details of the resource in the location element.</p>

<p><strong>Scenario: FHIR response bundles</strong></p>

<p>When a response bundle contains multiple resources, one or more of which cannot be populated as available data does not enable the resource in question to be populated to validate the associated profile, the provider will behave as follows: The request as a whole will error with a 500 HTTP Status returned, together with the appropriate OperationOutcome resource providing diagnostic detail of the error.</p>

<h2 id="fhir-resources">FHIR resources</h2>

<h3 id="resource-data-types">Resource data types</h3>
<p><a name="ResourceDataType"></a>
The FHIR specification defines a set of <a href="https://www.hl7.org/fhir/STU3/datatypes.html">data types</a> that are used for the resource elements.</p>

<p>The user locale (that is, user’s language, region and any special variant preferences that the user may want to see in their user interface) of a system SHALL NOT affect the FHIR on the wire representation of any data types (especially date-time and number formats).</p>

<p>Certain aspects of <a href="https://www.hl7.org/fhir/STU3/datatypes.html#primitive">primitive data type</a> representation warrant further consideration and SHALL be taken into consideration when designing and constructing FHIR resources.</p>

<p>For example:</p>

<ul>
  <li>leading 0 digits are not allowed</li>
  <li>strings SHALL NOT exceed 1MB in size</li>
  <li>URIs are case sensitive</li>
  <li>UUID values (urn:uuid:53fefa32-fcbb-4ff8-8a92-55ee120877b7) use all lower case</li>
  <li>dates have no time zone</li>
  <li>dates can be partial dates (for example, just ‘year’ or ‘year + month’)</li>
  <li>precision of the decimal value has significance</li>
  <li>primitive types other than string SHALL NOT have leading or trailing whitespace</li>
  <li><a href="https://www.hl7.org/fhir/STU3/json.html#null">use of null</a> and empty / zero length values in <a href="https://www.hl7.org/fhir/STU3/datatypes.html#1.19.0.1.1">XML and JSON representations</a></li>
</ul>

<h3 id="resource-narrative">Resource narrative</h3>

<p>The FHIR <a href="https://www.hl7.org/fhir/STU3/narrative.html">resource narrative</a> is not currently expected to be populated.</p>

<h3 id="resource-references">Resource references</h3>

<p>The FHIR resource model includes <a href="http://hl7.org/fhir/STU3/references.html">resource references</a> from one resource to another.</p>

<p>A reference can be either:</p>

<ul>
  <li>a relative or absolute URL to a resource managed by the same resource server (a local reference), or</li>
  <li>an absolute URL to a resource managed by another resource server (a remote reference)</li>
</ul>

<p>A provider’s ability to process a request relating to a resource may depend on its ability to utilise one or more resource references that the resource contains (for example, its ability to ‘follow the links’ to other resources).</p>

<h3 id="resource-metadata">Resource metadata</h3>

<p>Servers SHALL provide the <code class="highlighter-rouge">profile</code> <a href="https://www.hl7.org/fhir/STU3/resource.html#Meta">metadata</a> for each resource, asserting that the content conforms to one of the GP Connect resource profiles.</p>

<p>Servers SHALL provide the <code class="highlighter-rouge">version Id</code> metadata for each item. This SHALL change each time the content of the resource changes.</p>

<p>Consumer creating or amending a resource SHALL provide the <code class="highlighter-rouge">profile</code> metadata details within the sent resource. The <code class="highlighter-rouge">profile</code> metadata should be checked for by the provider to ensure predictable process and for forward compatibility when a server can handle multiple profiles for the same type of resource.</p>

<p>Clients SHALL use the <code class="highlighter-rouge">version Id</code> when performing updates to allow <a href="https://www.hl7.org/fhir/STU3/http.html#concurrency">management of resource contention</a> and to protect against <a href="http://www.w3.org/1999/04/Editing/">lost updates</a>.</p>

<h3 id="resource-transactions">Resource transactions</h3>

<p>When performing an update or creating <a href="https://www.hl7.org/fhir/STU3/http.html#transactional-integrity">resource transactions</a>, servers:</p>

<ul>
  <li>SHALL <strong>validate the content against valid profiles</strong> and business rules before creating/updating the resource</li>
  <li>MAY apply business rules that alter the content</li>
  <li>MAY merge updated content with existing content</li>
</ul>

<p>Servers SHALL validate the existence of any referenced resources when creating or updating a resource. For example, a <code class="highlighter-rouge">Slot</code> reference (for example, <code class="highlighter-rouge">Slot/D497DB00-99AA-11E5-A837-0800200C9A66</code>) used when creating a new <code class="highlighter-rouge">Appointment</code> would be checked for existence on the server and an error returned (and the create interaction aborted) if the slot does not exist.</p>

<p>Refer to the GitHub hosted <a href="https://github.com/nhsconnect/gpconnect-fhir">GP Connect FHIR repository</a> for the published FHIR profiles.</p>

<p>Refer to the <a href="https://www.hl7.org/fhir/STU3/validation.html#jar">HL7® FHIR® Validator</a> page for the most up to date details on how FHIR resources can be validated.</p>

<p>Servers SHALL provide a read interaction for every resource it accepts update interactions on.</p>

<p>Consumers SHALL follow the pattern described in the <a href="https://www.hl7.org/fhir/STU3/http.html#transactional-integrity">Transactional Integrity</a> section of the base FHIR specification, built on top of version-aware updates, for updating resources.</p>

<h2 id="fhir-resource-interactions">FHIR® resource interactions</h2>

<h3 id="requests">Requests</h3>

<p>Servers SHALL be able to consume and process the following requests for GP Connect FoT:</p>

<table>
  <thead>
    <tr>
      <th>Interaction</th>
      <th>Path</th>
      <th>Request verb</th>
      <th>Request content-type</th>
      <th>Body</th>
      <th>Prefer</th>
      <th>Conditional</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">read</code></td>
      <td><code class="highlighter-rouge">/[type]/[id]</code></td>
      <td><code class="highlighter-rouge">GET</code></td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td><code class="highlighter-rouge">ETag</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">update</code></td>
      <td><code class="highlighter-rouge">/[type]/[id]</code></td>
      <td><code class="highlighter-rouge">PUT</code></td>
      <td>R</td>
      <td>Resource</td>
      <td>O</td>
      <td><code class="highlighter-rouge">If-Match</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">delete</code></td>
      <td><code class="highlighter-rouge">/[type]/[id]</code></td>
      <td><code class="highlighter-rouge">DELETE</code></td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">create</code></td>
      <td><code class="highlighter-rouge">/[type]</code></td>
      <td><code class="highlighter-rouge">POST</code></td>
      <td>R</td>
      <td>Resource</td>
      <td>O</td>
      <td>N/A</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">search</code></td>
      <td><code class="highlighter-rouge">/[type]?</code></td>
      <td><code class="highlighter-rouge">GET</code></td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">(operation)</code></td>
      <td><code class="highlighter-rouge">/[type]/$[name]</code> <code class="highlighter-rouge">/[type]/[id]/$[name]</code></td>
      <td><code class="highlighter-rouge">POST</code> <br /> <code class="highlighter-rouge">GET</code></td>
      <td>R <br /> <code class="highlighter-rouge">application/x-www-form-urlencoded</code></td>
      <td>Parameters <br /> form data</td>
      <td>N/A</td>
      <td>N/A</td>
    </tr>
  </tbody>
</table>

<blockquote>
  <p>N/A = not present, R = required, O = optional</p>
</blockquote>

<h3 id="responses">Responses</h3>

<p>Servers SHALL be expected to produce the following responses for GP Connect FoT:</p>

<table>
  <thead>
    <tr>
      <th>Interaction</th>
      <th>Response content-type</th>
      <th>Body</th>
      <th>Location</th>
      <th>Content-location</th>
      <th>Versioning</th>
      <th>Status codes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">read</code></td>
      <td>R</td>
      <td>R: Resource</td>
      <td>N/A</td>
      <td>R</td>
      <td><code class="highlighter-rouge">ETag</code></td>
      <td><code class="highlighter-rouge">200</code>, <code class="highlighter-rouge">404</code>, <code class="highlighter-rouge">410</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">update</code></td>
      <td>R</td>
      <td>R: Resource</td>
      <td>N/A</td>
      <td>R</td>
      <td><code class="highlighter-rouge">ETag</code></td>
      <td><code class="highlighter-rouge">200</code>, <code class="highlighter-rouge">201</code>, <code class="highlighter-rouge">400</code>, <code class="highlighter-rouge">404</code> <code class="highlighter-rouge">405</code>, <code class="highlighter-rouge">409</code>, <code class="highlighter-rouge">412</code>, <code class="highlighter-rouge">422</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">delete</code></td>
      <td>R</td>
      <td>R: Operation Outcome</td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td><code class="highlighter-rouge">200</code>, <code class="highlighter-rouge">204</code>, <code class="highlighter-rouge">404</code>, <code class="highlighter-rouge">405</code>, <code class="highlighter-rouge">409</code>, <code class="highlighter-rouge">412</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">create</code></td>
      <td>R</td>
      <td>R: Resource</td>
      <td>R</td>
      <td>R</td>
      <td><code class="highlighter-rouge">ETag</code></td>
      <td><code class="highlighter-rouge">201</code>, <code class="highlighter-rouge">400</code>, <code class="highlighter-rouge">404</code> <code class="highlighter-rouge">405</code>, <code class="highlighter-rouge">422</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">search</code></td>
      <td>R</td>
      <td>R: Bundle</td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td><code class="highlighter-rouge">200</code>, <code class="highlighter-rouge">403</code></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">(operation)</code></td>
      <td>R</td>
      <td>R: Parameters/Resource</td>
      <td>N/A</td>
      <td>N/A</td>
      <td>N/A</td>
      <td><code class="highlighter-rouge">200</code>, <code class="highlighter-rouge">400</code>, <code class="highlighter-rouge">403</code>, <code class="highlighter-rouge">404</code>, <code class="highlighter-rouge">422</code></td>
    </tr>
  </tbody>
</table>

<blockquote>
  <p>N/A = not present, R = required, O = optional</p>
</blockquote>

<h4 id="response-codes">Response codes</h4>

<p>Servers SHALL produce the following main <a href="http://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml">HTTP status codes</a>:</p>

<table>
  <thead>
    <tr>
      <th>HTTP status code</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">200</code></td>
      <td>OK</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">201</code></td>
      <td>Created</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>Bad request</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">401</code></td>
      <td>Unauthorized</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>Forbidden</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>Not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">405</code></td>
      <td>Method not allowed</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">409</code></td>
      <td>Conflict</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">410</code></td>
      <td>Gone</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">412</code></td>
      <td>Precondition failed</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">415</code></td>
      <td>Unsupported media type</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">422</code></td>
      <td>Unprocessable entity</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">500</code></td>
      <td>Internal server error</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">501</code></td>
      <td>Not implemented</td>
    </tr>
  </tbody>
</table>

<h4 id="rejecting-updates"><a href="https://www.hl7.org/fhir/STU3/http.html#2.1.0.10.1">Rejecting updates</a></h4>

<p><a href="https://www.hl7.org/fhir/STU3/operationoutcome.html">OperationOutcome</a> may be returned with any HTTP <code class="highlighter-rouge">4xx</code> or <code class="highlighter-rouge">5xx</code> response, but is not required - many of these errors may be generated by generic server frameworks underlying a FHIR server.</p>

<p>Servers are permitted to reject update interactions because of integrity concerns or other business rules, and return HTTP status codes accordingly (usually a <code class="highlighter-rouge">422</code>).</p>

<p>As outlined in the FHIR specification, any of these errors SHOULD be accompanied by an <a href="https://www.hl7.org/fhir/STU3/operationoutcome.html">OperationOutcome</a> resource that provides additional detail concerning the issue.</p>

<p>Refer to <a href="development_fhir_error_handling_guidance.html">FHIR Guidance - Error Handling</a> for full details of error codes that SHALL be used when returning an operation outcome error.</p>

<h3 id="compartment-based-access">Compartment based access</h3>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>VERB [base]/[compartment_type]/[id]/[type]{?_format=[mime-type]}
</code></pre></div></div>

<p>Each resource type may belong to one or more logical <a href="http://hl7.org/fhir/STU3/compartmentdefinition.html">compartment</a>. A compartment is a logical grouping of resources which share a common property.</p>

<p>Servers SHALL support the <code class="highlighter-rouge">Patient</code> compartment for <code class="highlighter-rouge">Appointment</code> access.</p>

<p>The patient compartment includes any resources where the <code class="highlighter-rouge">subject</code> of the resource is the patient.</p>

<p>For example, to retrieve a list of all a patient’s appointments, use the URL:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient/[id]/Appointment
</span></code></pre></div></div>

<p>Servers SHALL support searching within this compartment by <code class="highlighter-rouge">start</code> and <code class="highlighter-rouge">end</code> date/time, for example:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient/[id]/Appointment?start=[{search_prefix}start_date]{&amp;start=[{search_prefix}end_date]}
</span></code></pre></div></div>

<h2 id="read-resource">Read resource</h2>

<p>A <a href="https://www.hl7.org/fhir/STU3/http.html#read">resource read</a> takes the following format:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/[type]/[id]{?_format=[mime-type]}
</span></code></pre></div></div>

<p>The returned resource SHALL have an <code class="highlighter-rouge">id</code> element with a value that is the [id].</p>

<p>Servers SHALL return an <code class="highlighter-rouge">ETag</code> header with the <code class="highlighter-rouge">version Id</code> of the resource.</p>

<h3 id="available-for-resources">Available for resources</h3>

<table>
  <thead>
    <tr>
      <th>Capability</th>
      <th>Resource(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Foundations</strong></td>
      <td><code class="highlighter-rouge">Patient</code>, <code class="highlighter-rouge">Practitioner</code>, <code class="highlighter-rouge">Organization</code></td>
    </tr>
    <tr>
      <td><strong>Access Record</strong></td>
      <td>TBC</td>
    </tr>
    <tr>
      <td><strong>Appointments</strong></td>
      <td><code class="highlighter-rouge">Appointment</code>, <code class="highlighter-rouge">Schedule</code>, <code class="highlighter-rouge">Slot</code>, <code class="highlighter-rouge">Location</code></td>
    </tr>
  </tbody>
</table>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> In workshop discussions with all principal GP system vendors it has been agreed that record locking (inside the GP system) will not impact on the ability of clients to query the GP Connect APIs and to obtain the latest saved/committed clinical and administrative data.</div>

<h3 id="retrieving-a-patient-resource-by-logical-id">Retrieving a patient resource by logical ID</h3>

<h4 id="request">Request</h4>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient/[id]
</span></code></pre></div></div>

<p>For example:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient/1A6E1B1C-6340-4663-926C-9CD1306EAAF8?_format=application/xml+fhir
</span></code></pre></div></div>

<div class="alert alert-success" role="alert"><i class="fa fa-check-square-o"></i> <b>Tip:</b> In this example the response format has been specified in the request URL using the <code class="highlighter-rouge">_format</code> parameter. This could also have been specified using the HTTP Accept header mechanism.</div>

<h4 id="response">Response</h4>

<div class="language-xml highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nt">&lt;Patient</span> <span class="na">xmlns=</span><span class="s">"http://hl7.org/fhir"</span><span class="nt">&gt;</span>
	<span class="nt">&lt;id</span> <span class="na">value=</span><span class="s">"1A6E1B1C-6340-4663-926C-9CD1306EAAF8"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;meta&gt;</span>
		<span class="nt">&lt;profile</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/StructureDefinition/gpconnect-patient-1"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;/meta&gt;</span>
	<span class="nt">&lt;identifier&gt;</span>
		<span class="nt">&lt;system</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/Id/nhs-number"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;value</span> <span class="na">value=</span><span class="s">"9900002831"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;/identifier&gt;</span>
	<span class="nt">&lt;identifier&gt;</span>
		<span class="nt">&lt;type&gt;</span>
			<span class="nt">&lt;coding&gt;</span>
				<span class="nt">&lt;system</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/ValueSet/gpconnect-patient-identifier-type-1"</span> <span class="nt">/&gt;</span>
				<span class="nt">&lt;code</span> <span class="na">value=</span><span class="s">"Local"</span> <span class="nt">/&gt;</span>
				<span class="nt">&lt;display</span> <span class="na">value=</span><span class="s">"Local identifier"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;/coding&gt;</span>
		<span class="nt">&lt;/type&gt;</span>
		<span class="nt">&lt;system</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/Id/local-identifier"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;value</span> <span class="na">value=</span><span class="s">"L12345"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;/identifier&gt;</span>
	<span class="nt">&lt;name&gt;</span>
		<span class="nt">&lt;use</span> <span class="na">value=</span><span class="s">"usual"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;family</span> <span class="na">value=</span><span class="s">"Taylor"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;given</span> <span class="na">value=</span><span class="s">"Sally"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;prefix</span> <span class="na">value=</span><span class="s">"Mrs"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;/name&gt;</span>
	<span class="nt">&lt;birthDate</span> <span class="na">value=</span><span class="s">"1947-06-09"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;address&gt;</span>
		<span class="nt">&lt;use</span> <span class="na">value=</span><span class="s">"home"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;type</span> <span class="na">value=</span><span class="s">"both"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;line</span> <span class="na">value=</span><span class="s">"42, Grove Street"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;city</span> <span class="na">value=</span><span class="s">"Overtown"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;district</span> <span class="na">value=</span><span class="s">"West Yorkshire"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;postalCode</span> <span class="na">value=</span><span class="s">"LS21 1PF"</span> <span class="nt">/&gt;</span>
	<span class="nt">&lt;/address&gt;</span>
<span class="nt">&lt;/Patient&gt;</span>
</code></pre></div></div>

<h2 id="create-resource">Create resource</h2>

<p>To <a href="https://www.hl7.org/fhir/STU3/http.html#create">create</a> a new resource a RESTful <strong>POST</strong> operation with a request body SHALL be used.</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">POST [base]/[resourcetype]
</span></code></pre></div></div>

<p>When the server creates a new resource and returns a <code class="highlighter-rouge">201</code> <strong>Created</strong> HTTP status code, it SHALL also return a <code class="highlighter-rouge">Location</code> header which contains the new <code class="highlighter-rouge">logical Id</code> and <code class="highlighter-rouge">version Id</code> of the created resource.</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">Location: [base]/[type]/[id]/_history/[vid]
</span></code></pre></div></div>

<p>[id] and [vid] are the newly created <code class="highlighter-rouge">logical Id</code> and <code class="highlighter-rouge">version Id</code> for the resource version. An <code class="highlighter-rouge">ETag</code> header with the <code class="highlighter-rouge">version Id</code> and a <code class="highlighter-rouge">Last-Modified</code> header will also be included in the response.</p>

<h3 id="available-for-resources-1">Available for resources</h3>

<table>
  <thead>
    <tr>
      <th>Capability</th>
      <th>Resource(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Foundations</strong></td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Access Record</strong></td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Appointments</strong></td>
      <td><code class="highlighter-rouge">Appointment</code></td>
    </tr>
  </tbody>
</table>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> In workshop discussions with all principal GP system vendors it has been agreed that record locking (inside the GP Community Independence Service (CIS)) will not impact on the ability of clients to query the GP Connect APIs and obtain the latest saved patient data.</div>

<h3 id="create-example-book-an-appointment-for-a-patient">Create example: Book an appointment for a patient</h3>

<p>Refer to <a href="appointments_use_case_book_an_appointment.html">Book an appointment</a> for request and response body examples for a create request.</p>

<h2 id="update-resource">Update resource</h2>

<p>To <a href="https://www.hl7.org/fhir/STU3/http.html#update">update</a> an existing resource, a RESTful <strong>PUT</strong> operation with a request body SHALL be used.</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">PUT [base]/[resourcetype]/[id]
</span></code></pre></div></div>

<p>The PUT operation will only be used to update existing resources. If the specified resource within the URL does not exist on the provider system an error SHALL be returned.</p>

<table>
  <thead>
    <tr>
      <th>Capability</th>
      <th>Resource(s)</th>
      <th>Field(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Foundations</strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Access Record</strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Appointments</strong></td>
      <td><code class="highlighter-rouge">Appointment</code></td>
      <td>reason, description, comment</td>
    </tr>
  </tbody>
</table>

<h3 id="update-example-modify-the-appointment-booking-reason">Update example: Modify the appointment booking reason</h3>

<p>Refer to <a href="appointments_use_case_amend_an_appointment.html">Amend an appointment</a> for request and response body examples for a request which updates a resource using the PUT HTTP verb.</p>

<h2 id="delete-resource">Delete resource</h2>

<p>To <a href="https://www.hl7.org/fhir/STU3/http.html#delete">delete</a> an existing resource, a RESTful <strong>DELETE</strong> operation with no request body SHALL be used.</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">DELETE [base]/[resourcetype]/[id]
</span></code></pre></div></div>

<table>
  <thead>
    <tr>
      <th>Capability</th>
      <th>Resource(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Foundations</strong></td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Access Record</strong></td>
      <td> </td>
    </tr>
    <tr>
      <td><strong>Appointments</strong></td>
      <td> </td>
    </tr>
  </tbody>
</table>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> GP Connect clients and servers are currently not expected to utilise the ability to delete a resource using the RESTful DELETE operation. However, this section is included as implementers should ensure that their implementation choices don’t preclude the use of this HTTP verb in future release.</div>

<h2 id="operations">Operations</h2>

<p><a href="https://www.hl7.org/fhir/STU3/operations.html">Operations</a> are used (a) where the server needs to play an active role in formulating the content of the response, not merely return existing information, or (b) where the intended purpose is to cause side effects such as the modification of existing resources, or creation of new resources.</p>

<p>As outlined in the <a href="https://www.hl7.org/fhir/STU3/profiling.html#api">Extend and Restricting the API</a> section of the FHIR® standard,  NHS Digital has decided to prefix its operation names with a short prefix (for example, <code class="highlighter-rouge">gpc</code>) followed by a ‘.’ to reduce the likelihood of name conflicts.</p>

<h2 id="search-resources">Search resources</h2>

<p>A simple <a href="https://www.hl7.org/fhir/STU3/http.html#search">search</a> is executed by performing a <code class="highlighter-rouge">GET</code> request optionally accompanied by zero or more name-value URL encoded parameters:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/[resourcetype]?name=value&amp;...
</span></code></pre></div></div>

<p>In order to enable searching by date/time range, servers SHALL support the following prefixes as defined in the base FHIR specification for date parameters: eq, gt, lt, ge, le.</p>

<p>To search for all the appointments for a patient that occurred over a 2-year period:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient/1A6E1B1C-6340-4663-926C-9CD1306EAAF8/Appointment?start=ge2014-01-01&amp;start=le2015-12-31
</span></code></pre></div></div>

<h3 id="chained-parameters">Chained parameters</h3>

<p>Servers SHALL support searching by a <a href="https://www.hl7.org/fhir/STU3/search.html#2.1.1.4.13">chained</a> <code class="highlighter-rouge">Patient</code> identifier parameter for references to <code class="highlighter-rouge">Patient</code> resources that conform to the <code class="highlighter-rouge">GP-Patient</code> profile (and therefore have an NHS number identifier). For example:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/AllergyIntolerance?patient.identifier=http://fhir.nhs.net/Id/nhs-number|1234569876
</span></code></pre></div></div>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> GP Connect clients and servers are not expected to support arbitrary ad hoc searching.</div>

<h3 id="search-example-search-for-a-patient-resource-by-business-id">Search example: Search for a patient resource by business ID</h3>

<h4 id="request-1">Request</h4>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Patient?identifier=http://fhir.nhs.net/Id/nhs-number|9900002831
</span></code></pre></div></div>

<p>If a patient resource for NHS number 9900002831 exists then the server SHALL return a bundle containing all patient resources with the specified NHS number identifier.</p>

<h4 id="response-1">Response</h4>

<div class="language-xml highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nt">&lt;Bundle&gt;</span>
	<span class="nt">&lt;Patient</span> <span class="na">xmlns=</span><span class="s">"http://hl7.org/fhir"</span><span class="nt">&gt;</span>
		<span class="nt">&lt;id</span> <span class="na">value=</span><span class="s">"1A6E1B1C-6340-4663-926C-9CD1306EAAF8"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;meta&gt;</span>
			<span class="nt">&lt;profile</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/StructureDefinition/gpconnect-patient-1"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;/meta&gt;</span>
		<span class="nt">&lt;identifier&gt;</span>
			<span class="nt">&lt;system</span> <span class="na">value=</span><span class="s">"http://fhir.nhs.net/Id/nhs-number"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;value</span> <span class="na">value=</span><span class="s">"9900002831"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;/identifier&gt;</span>
		<span class="nt">&lt;name&gt;</span>
			<span class="nt">&lt;use</span> <span class="na">value=</span><span class="s">"usual"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;family</span> <span class="na">value=</span><span class="s">"Smith"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;given</span> <span class="na">value=</span><span class="s">"Mike"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;prefix</span> <span class="na">value=</span><span class="s">"Mr"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;/name&gt;</span>
		<span class="nt">&lt;birthDate</span> <span class="na">value=</span><span class="s">"1977-01-09"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;address&gt;</span>
			<span class="nt">&lt;use</span> <span class="na">value=</span><span class="s">"home"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;type</span> <span class="na">value=</span><span class="s">"both"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;line</span> <span class="na">value=</span><span class="s">"2, The Green"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;city</span> <span class="na">value=</span><span class="s">"Harrogate"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;district</span> <span class="na">value=</span><span class="s">"Yorkshire"</span> <span class="nt">/&gt;</span>
			<span class="nt">&lt;postalCode</span> <span class="na">value=</span><span class="s">"HG1 4AF"</span> <span class="nt">/&gt;</span>
		<span class="nt">&lt;/address&gt;</span>
	<span class="nt">&lt;/Patient&gt;</span>
<span class="nt">&lt;/Bundle&gt;</span>
</code></pre></div></div>

<h3 id="advanced-search">Advanced search</h3>

<p>Servers SHALL implement the <a href="https://www.hl7.org/fhir/STU3/search.html#query">_query</a> search parameter to enable custom-named search profiles to be defined and used which describe a specific query operation.</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">

GET [base]/[resourcetype]?_query=[query_name]&amp;name=value&amp;...


</span></code></pre></div></div>

<p>Servers SHOULD implement the standard search equivalent of the advanced custom-named search for queries defined under the GP Connect FoT.</p>

<h4 id="request-2">Request</h4>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">GET [base]/Schedule?_query=getschedule&amp;date=ge2016-05-12&amp;date=le2016-05-26
</span></code></pre></div></div>

<h4 id="response-2">Response</h4>

<div class="language-xml highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nt">&lt;Bundle</span> <span class="na">xmlns=</span><span class="s">"http://hl7.org/fhir"</span><span class="nt">&gt;</span>
	 <span class="nt">&lt;type</span> <span class="na">value=</span><span class="s">"searchset"</span><span class="nt">/&gt;</span>
<span class="nt">&lt;/Bundle&gt;</span>
</code></pre></div></div>




    

</div>





</div>
    
</div>
<!-- /.container -->
</div>
   

   
