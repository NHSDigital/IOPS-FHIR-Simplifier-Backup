## {{page-title}}

### Authorise a proxy to act on behalf of a patient

<table class="assets" title="PDS Use Case 1">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> proxy,<br>
        <strong>I need</strong> to be able to access services for a patient I care for,<br>
        <strong>So that</strong> I can support them with their care.<br><br>
        
        <strong>As a</strong> patient,<br>
        <strong>I need</strong> to be able to share access to my services with someone I trust,<br>
        <strong>So that</strong> I can be supported in my care.<br><br>
        
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to be able to authorise proxy access,<br>
        <strong>So that</strong> I can enable proxies to support patients in their care.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxy, Patient, Clinical Professional</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>
        Every time access is requested by a proxy or a patient.<br>
        Every time a clinical professional decides that access may be beneficial as part of a regular care interaction.
      </td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        A proxy or patient makes a request for access using a patient-facing service.<br>
        A clinical professional authorises access in their clinical system.
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Proxy’s identifier (NHS number).</li>
          <li>Patient’s identifier (NHS number).</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy is granted proxy access to a patient’s services.</li>
          <li>A message to the patient is sent if their consent is required to approve the request.</li>
          <li>In this case, their consent will be recorded as part of the request upon their approval and sent to the relevant clinical professional.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <ol>
          <li>A patient or proxy requests access through a digital application or in-person as part of a regular care interaction.</li>
          <li>The clinical professional creates a relationship, granting proxy access so that the proxy can act on behalf of a patient.</li>
          <li>Any pre-existing request for access is then updated and marked as ‘approved.’</li>
          <li>The proxy and, where appropriate, patient get notified about the request being approved and/or access being granted.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>The proxy or patient do not meet the eligibility criteria for access. For example, they may not be at the same GP practice.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>The clinical professional is not sufficiently verified or authenticated.</li>
          <li>The proxy or patient does not have a valid PDS record.</li>
          <li>Invalid or missing patient identifier.</li>
          <li>Invalid or missing proxy identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>

