## {{page-title}}

### 	Request proxy access to act on behalf of a patient

<br>

<table class="assets" title="Proxy Access Use Case">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> proxy,<br>
        <strong>I need</strong> to be able to request access to act on behalf of a patient I care for,<br>
        <strong>So that</strong> I can access services for them to support them with their care.<br><br>
        
        <strong>As a</strong> patient with capacity,<br>
        <strong>I need</strong> to be able to nominate a proxy to act on my behalf,<br>
        <strong>So that</strong> I can be supported in my care by a trusted individual.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies, Patients, Clinical professional / General practitioner</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Every time a proxy or patient requests proxy access.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>A proxy or patient requests proxy access using a patient-facing service.</td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy’s and patient’s identifiers (NHS numbers) are provided.</li>
          <li>The proxy or patient’s identity is suitably verified and authenticated at the point when the request is made.</li>
          <li>Where they are nominating a proxy, the patient’s consent is captured as part of the request.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>A request for access has been recorded.</li>
          <li>Where a patient has capacity or is deemed competent, their consent has been solicited and recorded.</li>
          <li>A decision to grant or refuse the establishment of the proxy relationship has been made and recorded by the clinical professional.</li>
          <li>If authorized, an active proxy relationship has been established, the clinical professional has performed any necessary redactions to the patient record and local permissions for online access have been set up.
          <li>The proxy has been informed of their access being set up.</li>
            
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <ol>
          <li>The proxy or patient makes a request for access using a patient-facing service. They receive confirmation of their request being received.</li>
          <li>The patient accepts a proxy access request within a patient-facing service if the request requires their consent to be approved. If this is not possible, the clinical professional will obtain the patient’s consent to inform their authorisation decision.</li>
          <li>The request for access is sent to the patient’s general practitioner for authorisation.</li>
          <li>The clinical professional views the request and determines whether the proxy relationship is safe and appropriate.</li>
          <li>If the relationship is authorised and records access is being granted, the clinical professional will review and redact the record accordingly.</li>
          <li>If the relationship is authorised, the clinical professional will set up local permissions for the proxy to access online services.</li>
          <li>The proxy is notified if the proxy access has been set up.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>The proxy or patient does not meet the eligibility criteria for access. For example, they may be sensitive flagged (S-flagged) in PDS.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>Proxy or patient is not sufficiently verified or authenticated.</li>
          <li>The proxy or patient does not have a valid PDS record.</li>
          <li>Invalid or missing patient identifier.</li>
          <li>Invalid or missing proxy identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>

