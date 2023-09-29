## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">Error handling</h1>
</div>

<div class="post-content">
   
<div class="summary"><b>Summary:</b> Details of the common error handling pattern(s) across the GP Connect API</div>
   

   

    
    
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

    

<br/>

<p>As a nationally brokered FHIR® API, the GP Connect error handling approach defined below closely follows the approach of the Spine Core FHIR API Framework.</p>

<p>However, the guidance given below is the definitive error handling definition for the GP Connect API and thus the <a href="https://developer.nhs.uk/apis/spine-core-1-0/resources_error_handling.html">Spine Core error handling guidance</a> should be viewed for context only.</p>

<h3 id="operation-outcome-usage">Operation outcome usage</h3>

<p>In the event of an error, provider systems <strong>SHALL</strong> respond by providing an OperationOutcome resource profiled to <a href="https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1">GPConnect-OperationOutcome-1</a>.</p>

<p>The <code class="highlighter-rouge">GPConnect-OperationOutcome-1</code>:</p>
<ul>
  <li><strong>SHALL</strong> contain a definition of severity in the <code class="highlighter-rouge">OperationOutcome.issue.severity</code> field providing a value from the <a href="http://hl7.org/fhir/STU3/valueset-issue-severity.html">valueset-issue-severity</a> value set. In all cases described in this guidance, the value used will be <code class="highlighter-rouge">error</code>.</li>
  <li><strong>SHALL</strong> contain a definition of the type of error in the <code class="highlighter-rouge">OperationOutcome.issue.code</code> element, providing a value from the <a href="http://hl7.org/fhir/STU3/valueset-issue-type.html">issue-type</a> value set.</li>
  <li><strong>SHALL</strong> contain details of the <code class="highlighter-rouge">Spine error code</code> in the <code class="highlighter-rouge">OperationOutcome.issue.details.coding.code</code> and <code class="highlighter-rouge">OperationOutcome.issue.details.coding.display</code> fields. These shall be taken from the standard set of NHS Spine error codes as defined in the <a href="https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1">spine-error-or-warning-code-1</a> value set. The Spine error and warning codes provide a greater degree of error handling granularity, and also ensure a standardised error handling approach across NHS APIs.</li>
  <li><strong>SHOULD</strong> provide additional diagnostic details of the error in the <code class="highlighter-rouge">OperationOutcome.diagnostics</code> property where such details securely provide additional error context for consumer applications.</li>
</ul>

<p>The sections below provide guidance on the error details to be returned in a number of key scenarios.</p>

<h3 id="identity-validation-errors">Identity validation errors</h3>

<p>Provider systems <strong>SHALL</strong> respond by returning one of the following <code class="highlighter-rouge">OperationOutcome</code> error codes where FHIR resource identity error scenarios are encountered:</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>value</td>
      <td>INVALID_IDENTIFIER_SYSTEM</td>
      <td>Invalid identifier system</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>value</td>
      <td>INVALID_IDENTIFIER_VALUE</td>
      <td>Invalid identifier value</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>value</td>
      <td>INVALID_NHS_NUMBER</td>
      <td>Invalid NHS number</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>business-rule</td>
      <td>INVALID_PATIENT_DEMOGRAPHICS</td>
      <td>Invalid patient demographics (that is, PDS trace failed)</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>ORGANISATION_NOT_FOUND</td>
      <td>Organisation not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>PATIENT_NOT_FOUND</td>
      <td>Patient not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>PRACTITIONER_NOT_FOUND</td>
      <td>Practitioner not found</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">404</code></td>
      <td>not-found</td>
      <td>NO_RECORD_FOUND</td>
      <td>No record found</td>
    </tr>
  </tbody>
</table>

<h4 id="example-invalid-nhs-number-supplied">Example: Invalid NHS number supplied</h4>

<p>If an invalid NHS number value is supplied to the <code class="highlighter-rouge">$gpc.getstructuredrecord</code> operation, the following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span>
      <span class="s2">
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"
 </span>
      
      <span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"value"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"INVALID_NHS_NUMBER"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Invalid NHS number"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>


<h4 id="example-patient-not-found">Example: Patient not found</h4>

<p>For example, if a valid NHS number value is supplied to the <code class="highlighter-rouge">$gpc.getstructuredrecord</code> operation but no active GP record exists for that patient, then the following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"not-found"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"PATIENT_NOT_FOUND"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient not found"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="example-resource-not-found">Example: Resource not found</h4>

<p>This is a catch-all where a request for a resource instance cannot be found at the FHIR server, where more specific Spine error codes (such as PATIENT_NOT_FOUND) cannot be used.</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"not-found"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"NO_RECORD_FOUND"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"No record found"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="security-validation-errors">Security validation errors</h3>

<p>When responding to consumer API requests, provider systems <strong>SHALL</strong> return one of the following <code class="highlighter-rouge">OperationOutcome</code> details when enforcement of local consent rules result in an error condition:</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>NO_PATIENT_CONSENT</td>
      <td>Patient has not provided consent to share data</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>NO_ORGANISATION_CONSENT</td>
      <td>Organisation has not provided consent to share data</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>ACCESS DENIED</td>
      <td>Access denied</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>NO_RELATIONSHIP</td>
      <td>No legitimate relationship exists with this patient</td>
    </tr>
  </tbody>
</table>

<h4 id="example-no-patient-consent-to-share">Example: No patient consent to share</h4>

<p>For example, if the patient has requested that their record should not be shared then the following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"NO_PATIENT_CONSENT"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient has not provided consent to share data"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="example-access-denied">Example: Access denied</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ACCESS DENIED"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Access denied"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"The Access Document capability is disabled at this practice."</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="duplicate-errors">Duplicate errors</h3>

<p>When responding to consumer API requests, provider systems <strong>SHALL</strong> return one of the following <code class="highlighter-rouge">OperationOutcome</code> details when a resource could not be created or updated because it would cause a duplicate in the provider system:</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">409</code></td>
      <td>duplicate</td>
      <td>DUPLICATE_REJECTED</td>
      <td>Create would lead to creation of a duplicate resource</td>
    </tr>
  </tbody>
</table>

<h4 id="example-attempting-to-register-a-patient-that-already-exists">Example: Attempting to register a patient that already exists</h4>

<p>For example, if the consumer attempted to register a patient that already has an active record on the provider system the error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"duplicate"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"DUPLICATE_REJECTED"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Create would lead to creation of a duplicate resource"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient record already exists with that NHS number"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="resource-validation-errors">Resource validation errors</h3>

<p>Where FHIR resource validation issues arise during processing of consumer requests, provider systems <strong>SHALL</strong> utilise one the following error details:</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">422</code></td>
      <td>invalid</td>
      <td>INVALID_RESOURCE</td>
      <td>Invalid validation of resource</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">422</code></td>
      <td>invalid</td>
      <td>INVALID_PARAMETER</td>
      <td>Invalid parameter</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">422</code></td>
      <td>invalid</td>
      <td>REFERENCE_NOT_FOUND</td>
      <td>Reference not found</td>
    </tr>
  </tbody>
</table>

<p>Detailed diagnostic information <strong>MUST</strong> be supplied when erroring on the codes above.</p>

<p>INVALID_PARAMETER would be used in the following, or similar, scenarios:</p>
<ul>
  <li>Unexpected parameter value for a custom operation. For example, a lowercase value is supplied to the recordSection parameter of the $gpc.getcarerecord operation.</li>
  <li>An invalid date/time value specified in a custom operation parameter. For example, an invalid timePeriod defined in the timePeriod input parameter to the $gpc.getcarerecord operation.</li>
</ul>

<p>INVALID_RESOURCE would be used in situations such as the following:</p>
<ul>
  <li>Resource fails to validate against StructureDefinition (either in request body or in JSON Web Tokens (JWT) claim).</li>
  <li>A resource fails to be processed because of a FHIR constraint, or other rule application, where the error is not already covered by other error codes</li>
</ul>

<p>REFERENCE_NOT_FOUND describes a scenario where a consumer POSTs a FHIR resource which contains a FHIR reference that cannot be found.</p>

<h4 id="example-reference-not-found">Example: Reference not found</h4>

<p>For example, when using the ‘Book an appointment’ API use case, a consumer includes a reference to a slot which does not exist at the server. The following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"invalid"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"REFERENCE_NOT_FOUND"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Reference not found"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Reference to Slot/6 - no such slot exists at the server"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="malformed-request-errors">Malformed request errors</h3>

<p>When the server cannot or will not process a request due to an apparent client error then the following <code class="highlighter-rouge">BAD_REQUEST</code> error <strong>SHALL</strong> be used to return debug details.</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>invalid</td>
      <td>BAD_REQUEST</td>
      <td>Submitted request is malformed/invalid</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>invalid</td>
      <td>CONFLICTING_VALUES</td>
      <td>Conflicting values have been specified in different fields</td>
    </tr>
  </tbody>
</table>

<p>BAD_REQUEST Spine error codes should be used in the following types of scenario:</p>
<ul>
  <li>JWT claims information is not valid JSON, is null, or has an invalid value</li>
  <li>invalid FHIR resource in JWT claim (for example, patient resource when practitioner expected)</li>
  <li>malformed JSON or XML content in request body</li>
  <li>an expected header (for example, <code class="highlighter-rouge">interaction ID header</code>) is missing or invalid</li>
  <li>invalid HTTP verb used (for example, using POST to read a patient)</li>
  <li>InteractionID header does not match request</li>
</ul>

<h4 id="example-malformed-json-claim-in-request">Example: Malformed JSON claim in request</h4>

<p>For example, if the request contained a null <code class="highlighter-rouge">aud</code> claim in the JWT, then the following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"invalid"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"BAD_REQUEST"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Bad request"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Empty JWT aud claim"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="internal-server-errors">Internal server errors</h3>

<p>When the FHIR server has received a request for an operation or FHIR resource which is not (yet) implemented, then the NOT_IMPLEMENTED Spine error code <strong>SHALL</strong> be used.</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">501</code></td>
      <td>not-supported</td>
      <td>NOT_IMPLEMENTED</td>
      <td>Not implemented</td>
    </tr>
  </tbody>
</table>

<p>When the error is <strong>unexpected</strong> and the server can’t be more specific on the exact nature of the problem then the <code class="highlighter-rouge">INTERNAL_SERVER_ERROR</code> Spine error code <strong>SHALL</strong> be used, and diagnostics <strong>SHALL</strong> be included to provide detail of the error.</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Spine error code - code</th>
      <th>Spine error code - display</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">500</code></td>
      <td>processing</td>
      <td>INTERNAL_SERVER_ERROR</td>
      <td>Unexpected internal server error</td>
    </tr>
  </tbody>
</table>

<h4 id="example-unexpected-exception">Example: Unexpected exception</h4>

<p>For example, if an unexpected internal exception is thrown by either an Operation or RESTful API, then the following error details would be returned:</p>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
      </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-OperationOutcome-1"</span><span class="w">
    </span><span class="p">]</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"exception"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"INTERNAL_SERVER_ERROR"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Internal server error"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Any further internal debug details i.e. stack trace details etc."</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h3 id="spine-secure-proxy-ssp-errors">Spine Secure Proxy (SSP) errors</h3>

<p>When the Spine Secure Proxy cannot or will not process a request then one of the following errors are used to return debug details:</p>

<table>
  <thead>
    <tr>
      <th>HTTP code</th>
      <th>Issue type</th>
      <th>Description of error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">400</code></td>
      <td>invalid</td>
      <td>Target URL varies from endpoint registered in SDS</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>Sender ASID is not authorised for this interaction</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>Receiver ASID is not authorised for this interaction</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">403</code></td>
      <td>forbidden</td>
      <td>Sender ASID is not authorised to send the interaction to receiver ASID</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">405</code></td>
      <td>not-supported</td>
      <td>Method not allowed</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">415</code></td>
      <td>not-supported</td>
      <td>Unsupported media type</td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">502</code></td>
      <td>transient</td>
      <td>Error communicating to target URL</td>
    </tr>
  </tbody>
</table>

<h4 id="ssp-error-example-target-url-varies-from-endpoint-registered-in-sds">SSP error example: Target URL varies from endpoint registered in SDS</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"09a01679-2564-0fb4-5129-aecc81ea2706"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"invalid"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"400"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ENDPOINT_https://supplier.thirdparty.nhs.uk/v1/fhir/_CPAID_S000000000001_VARIES_FROM_TARGETURL_https://supplier.thirdparty.nhs.uk/v1/test"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">]</span><span class="w">
            </span><span class="p">},</span><span class="w">
            </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ENDPOINT_https://supplier.thirdparty.nhs.uk/v1/fhir/_CPAID_S000000000001_VARIES_FROM_TARGETURL_https://supplier.thirdparty.nhs.uk/v1/test"</span><span class="p">,</span><span class="w">
        </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-sender-asid-is-not-authorised-for-this-interaction">SSP error example: Sender ASID is not authorised for this interaction</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"10960df2-29d1-4e71-823c-c0bb9d723012"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"403"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ASID_CHECK_FAILED_MESSAGESENDER_100000000001"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">]</span><span class="w">
            </span><span class="p">},</span><span class="w">
            </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ASID_CHECK_FAILED_MESSAGESENDER_100000000001"</span><span class="w">
        </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-receiver-asid-is-not-authorised-for-this-interaction">SSP error example: Receiver ASID is not authorised for this interaction</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"018C2550-358F-4F68-BE19-88C80A859E0A"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"403"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"PARTYKEY_INTERACTION_CHECK_FAILED_MESSAGERECEIVER_200000000002"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">]</span><span class="w">
            </span><span class="p">},</span><span class="w">
            </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"PARTYKEY_INTERACTION_CHECK_FAILED_MESSAGERECEIVER_200000000002"</span><span class="w">
        </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-sender-asid-is-not-authorised-to-send-the-interaction-to-receiver-asid">SSP error example: Sender ASID is not authorised to send the interaction to receiver ASID</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"43A8BB0D-195E-4CF4-86F9-E8514F6EB585"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"403"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"FOT_CHECK_FAILED_MESSAGESENDER_200000000001_MESSAGERECEIVER_200000000002"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">]</span><span class="w">
            </span><span class="p">},</span><span class="w">
            </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"FOT_CHECK_FAILED_MESSAGESENDER_200000000001_MESSAGERECEIVER_200000000002"</span><span class="w">
        </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-method-not-allowed">SSP error example: Method not allowed</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"forbidden"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"fatal"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"405"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/StructureDefinition/spine-operationoutcome-1"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"405: Method Not Allowed"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">}</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-unsupported-media-type">SSP error example: Unsupported media type</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"09a01679-2564-0fb4-5129-aecc81ea2706"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"not-supported"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"415"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Unsupported_Media_Type"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Unsupported_Media_Type"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>

<h4 id="ssp-error-example-error-communicating-to-target-url">SSP error example: Error communicating to target URL</h4>

<div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"OperationOutcome"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"78D536C0-44D6-11E9-BFCD-17C1B88243CD"</span><span class="p">,</span><span class="w">
  </span><span class="s2">"issue"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"transient"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"severity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"error"</span><span class="p">,</span><span class="w">
      </span><span class="s2">"details"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
          </span><span class="p">{</span><span class="w">
            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ERROR_COMMUNICATING_TO_ENDPOINT_URL_https://supplier.thirdparty.nhs.uk/D11111/STU3/1/GPConnect/Patient"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"502"</span><span class="p">,</span><span class="w">
            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://fhir.nhs.net/ValueSet/gpconnect-schedule-response-code-1-0"</span><span class="w">
          </span><span class="p">}</span><span class="w">
        </span><span class="p">]</span><span class="w">
      </span><span class="p">},</span><span class="w">
      </span><span class="s2">"diagnostics"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ERROR_COMMUNICATING_TO_ENDPOINT_URL_https://supplier.thirdparty.nhs.uk/D11111/STU3/1/GPConnect/Patient"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span><span class="w">
</span></code></pre></div></div>




    

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