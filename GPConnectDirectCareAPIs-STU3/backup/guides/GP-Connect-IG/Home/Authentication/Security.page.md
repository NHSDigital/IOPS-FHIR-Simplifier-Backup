<div class="post-header">
   <h1 class="post-title-main">Security</h1>
</div>





<div class="post-content">

   
<div class="summary"><b>Summary: </b>Details of the API security model and supported protocols</div>
   

   

    
    
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

    

  <h2 id="secure-connection-negotiation">Secure connection negotiation</h2>

<p>Provider systems:</p>

<ul>
  <li>
    <p>SHALL only accept connections from the <a href="integration_spine_secure_proxy.html">Spine Secure Proxy</a> (SSP)</p>
  </li>
  <li>
    <p>SHALL authenticate the SSP prior to responding to any requests using its <a href="development_api_security_guidance.html#client-certificates-tlsma">client certificate</a></p>
  </li>
  <li>
    <p>SHALL only permit approved <a href="development_api_security_guidance.html#supported-ciphers">supported ciphers</a> to be utilised</p>
  </li>
  <li>
    <p>SHALL only accept encrypted connections and drop connection attempts presented over insecure protocols</p>
  </li>
  <li>
    <p>SHALL only accept requests for its allocated address space identifier (ASID), as specified by the <code class="highlighter-rouge">Ssp-To</code> header  on its matching endpoint URL</p>
  </li>
  <li>
    <p>SHALL check that the <code class="highlighter-rouge">Ssp-InteractionID</code> value is consistent with the endpoint being requested</p>
  </li>
  <li>
    <p>SHALL check for the presence of all <a href="https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html#consumer">SSP headers</a></p>
  </li>
  <li>
    <p>SHALL check that an <a href="integration_cross_organisation_audit_and_provenance.html#json-web-tokens-jwt">authorization bearer token</a> is present and correctly formed</p>
  </li>
  <li>
    <p>MAY authorise access to API endpoints through examining acceptable values in the JSON Web Tokens (JWT) requested_scope claim</p>
  </li>
  <li>
    <p>SHALL risk-manage the security of the endpoints of the Transport Layer Security (TLS) communications, so as to prevent inappropriate risks (for example, audit logging of the GET parameters into an unprotected audit log)</p>
  </li>
</ul>

<h2 id="security-testing">Security testing</h2>

<p>Provider systems SHALL as a minimum be tested against the <a href="https://www.owasp.org/index.php/Top_10_2013-Top_10">OWASP top 10 web application vulnerabilities</a>.</p>

<p>Provider systems SHOULD be tested for vulnerability to Denial of Service (DoS) and hardened against such attacks.</p>

<h2 id="secure-socket-layer-ssl-and-transport-layer-security-tls-protocols">Secure Socket Layer (SSL), and Transport Layer Security (TLS) protocols</h2>

<p>After consultation with the Infrastructure Security, Operational Security and Spine DDC teams, the following SSL protocol guidance have been agreed:</p>

<ul>
  <li>suppliers SHALL use <code class="highlighter-rouge">TLS1.2</code> with mutual authentication enabled for all message interactions</li>
  <li>suppliers SHALL NOT use <code class="highlighter-rouge">TLS1.0</code>, <code class="highlighter-rouge">TLS1.1</code>, <code class="highlighter-rouge">SSLv2</code> and <code class="highlighter-rouge">SSLv3</code></li>
</ul>

<h2 id="supported-ciphers">Supported ciphers</h2>

<p>After consultation with the Infrastructure Security, Operational Security and Spine DDC teams the following SSL protocols SHALL be supported.</p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> The list of supported ciphers is ordered by preference (that is, the first item being the most preferred).</div>

<ul>
  <li><code class="highlighter-rouge">AESGCM+EECDH</code></li>
  <li><code class="highlighter-rouge">AESGCM+EDH</code></li>
  <li><code class="highlighter-rouge">AES256+EECDH</code></li>
  <li><code class="highlighter-rouge">AES256+EDH</code></li>
</ul>

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> Galois/Counter Mode (GCM) suites are preferred as these are resistant to timing attacks<sup>1</sup>.</div>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> A Java Runtime Environment 8 (or above) and/or an up to date version of OpenSSL is required to support the GCM cipher suites.</div>

<p><sup>1</sup><a href="https://www.digicert.com/ssl-support/ssl-enabling-perfect-forward-secrecy.htm">Digitcert - SSL Support Enabling Perfect Forward Secrecy</a></p>

<h2 id="tomcat-openssl-support-using-the-apache-portable-runtime-aprnative-provider">Tomcat OpenSSL support using the Apache Portable Runtime (APR)/native provider</h2>

<ul>
  <li>SSLCipherSuite = <code class="highlighter-rouge">AESGCM+EECDH,AESGCM+EDH,AES256+EECDH,AES256+EDH</code></li>
  <li>SSLHonorCipherOrder = <code class="highlighter-rouge">true</code></li>
  <li>SSLProtocol = <code class="highlighter-rouge">TLSv1.2</code></li>
  <li>SSLVerifyClient = <code class="highlighter-rouge">require</code></li>
</ul>

<p>Please see the <a href="https://tomcat.apache.org/tomcat-8.0-doc/config/http.html#SSL_Support">Tomcat Config HTTP SSL Support</a> web page for more details.</p>

<h2 id="client-certificates-tlsmutual-authentication-ma">Client certificates (TLS/mutual authentication (MA))</h2>

<p>Provider and consumer systems SHALL only accept client certificates issued by the NHS Digital Deployment Issue and Resolution (DIR) team.</p>

<p>Provider and consumer systems SHALL only accept client certificates with a valid Spine ‘chain of trust’ (that is, linked to the Spine SubCA and RootCA).</p>

<p>Provider and consumer systems SHALL only accept client certificates which have not expired or been revoked.</p>

<p>Provider and consumer systems SHALL check the <code class="highlighter-rouge">FQDN</code> presented in the client certificate is that of the <a href="https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html">Spine Security Proxy</a> (SSP).</p>

<h2 id="response-headers">Response headers</h2>

<p>Provider systems SHALL ensure no sensitive data leaks into a browser cache by setting the following cache headers on all responses:</p>

<div class="language-http highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="err">Cache-Control: no-store
</span></code></pre></div></div>

<h2 id="authorisation-of-access-to-endpoints">Authorisation of access to endpoints</h2>

<p>The primary purpose of the JWT claims is to <a href="integration_cross_organisation_audit_and_provenance.html#cross-organisation-audit--provenance-transport">enable cross organisation provenance</a> information to be transmitted for auditing purposes.</p>

<p>Provider systems MAY choose to use the value of the requested_scope claim to authorise access to APIs. In this case, provider systems SHALL apply authorisation logic to endpoints as follows:</p>

<table>
  <thead>
    <tr>
      <th>Endpoint</th>
      <th>Acceptable values of requested_scope JWT claim</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/Patient</td>
      <td>patient/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Organization</td>
      <td>organization/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Appointment</td>
      <td>patient/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Practitioner</td>
      <td>organization/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Location</td>
      <td>organization/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Slot</td>
      <td>organization/*.[read/write]</td>
    </tr>
    <tr>
      <td>/DocumentReference</td>
      <td>patient/*.[read/write]</td>
    </tr>
    <tr>
      <td>/Binary</td>
      <td>patient/*.[read/write]</td>
    </tr>
  </tbody>
</table>

<h2 id="external-policy-documents">External policy documents</h2>

<table>
  <tbody>
    <tr>
      <td>Name</td>
      <td>Author</td>
      <td>Version</td>
      <td>Updated</td>
    </tr>
    <tr>
      <td><a href="http://webarchive.nationalarchives.gov.uk/20161021125701/http:/systems.digital.nhs.uk/infogov/security/infrasec/gpg/acs.pdf">Approved Cryptographic Algorithms Good Practice Guidelines</a></td>
      <td>NHS Digital</td>
      <td>v4.0</td>
      <td>July 2016</td>
    </tr>
    <tr>
      <td><a href="https://digital.nhs.uk/spine/technical-information-warranted-environment-specification">Warranted Environment Specification (WES)</a></td>
      <td>NHS Digital</td>
      <td>v1.0</td>
      <td>June 2015</td>
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