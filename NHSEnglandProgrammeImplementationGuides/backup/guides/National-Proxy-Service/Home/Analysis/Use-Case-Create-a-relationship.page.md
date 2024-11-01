## {{page-title}}

<table class="assets" title="PDS Use Case 1">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td><strong>As a</strong> proxy,<br><strong>I need</strong> to be able to request access to act on behalf of a patient I care for,<br><strong>So that</strong> I can access services for them to support them with their care.<br><br>
          <strong>As a</strong> patient with capacity,<br><strong>I need</strong> to be able to nominate a proxy to act on my behalf,<br><strong>So that</strong> I can be supported in my care by a trusted individual.</td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies and Patients</td>
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
      <td><strong>Pre Conditions</strong></td>
      <td><ol><li>The proxy’s and patient’s identifiers (NHS numbers) are provided.</li><li>Where they are nominating a proxy, the patient’s consent is captured as part of the request.</li></ol></td>
    </tr>
    <tr>
      <td><strong>Post Conditions</strong></td>
      <td><ol><li>A request is created and sent to the relevant clinical professional.</li><li>A message to the patient is sent if their consent is required to approve the request.</li><li>In this case, their consent will be recorded as part of the request upon their approval and sent to the relevant clinical professional.</li></ol></td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td><ol><li>The proxy or patient makes a request for access using a patient-facing service. They receive confirmation of their request being sent.</li><li>The patient consents to proxy access within a patient-facing service if the request requires their consent to be approved.
If this is not possible, then the clinical professional will manually obtain the patient’s consent at the point of authorisation.</li><li>The request for access is sent to the relevant clinical professional for authorisation.</li><li>The clinical professional views the request and decides whether the proxy should have proxy access to the patient’s services.</li></ol></td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>The proxy or patient do not meet the eligibility criteria for access. For example, they may not be at the same GP practice.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td><ol><li>Proxy or patient is not sufficiently verified or authenticated.</li><li>The proxy or patient does not have a valid PDS record.</li><li>Invalid or missing patient identifier.</li><li>Invalid or missing proxy identifier.</li></ol></td>
    </tr>
  </tbody>
</table>
<br>