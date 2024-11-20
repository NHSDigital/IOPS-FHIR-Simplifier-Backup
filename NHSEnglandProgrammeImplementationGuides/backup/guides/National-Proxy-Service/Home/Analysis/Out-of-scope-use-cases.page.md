## {{page-title}}

### Enable a proxy to act on behalf of a patient

<table class="assets" title="PDS Use Case 4">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> service provider,<br>
        <strong>I need</strong> to know what a proxy can do on behalf of a specific patient,<br>
        <strong>So that</strong> I can enforce appropriate access controls within my service.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Patient-facing services and clinical systems (service providers)</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Every time a proxy accesses services for a patient.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        A proxy accesses services for a patient in a patient-facing service.<br>
        A service provider views the patient(s) a proxy can act on behalf of, the proxy’s relationship to the patient(s), and what the proxies can do for them, to enforce access controls within their service.
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Proxy’s identifier (NHS number)</li>
          <li>Patient’s identifier (NHS number)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy can view the patients they can act on behalf of, the nature of their relationship to them, and the services they can access for each patient, in a patient-facing service.</li>
          <li>The service provider can see the patients the proxy can act on behalf of, the nature of their relationship to them, and the services they can access for each patient.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <ol>
          <li>An authenticated service provider views the patients that the proxy can act on behalf of, and the services they can access for each patient.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>The proxy has no patients they can act on behalf of.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>The service provider is not sufficiently verified or authenticated.</li>
          <li>Invalid or missing proxy identifier.</li>
          <li>Invalid or missing patient identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>


### Manage what a proxy is allowed to do for a patient

<table class="assets" title="PDS Use Case 5">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> patient,<br>
        <strong>I need</strong> to manage what a proxy is allowed to do for me,<br>
        <strong>So that</strong> I am appropriately supported in my care in line with my needs.<br><br>
        
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to manage what a proxy is allowed to do for a patient,<br>
        <strong>So that</strong> I can ensure a patient is appropriately supported in their care.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies, Clinical professionals</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>
        Every time a patient changes what proxies can do on their behalf.<br>
        Every time a clinical professional changes what a proxy can do on behalf of a patient, or the basis on which the proxy has access.
      </td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        A patient changes a proxy’s permissions within a patient-facing service.<br>
        A clinical professional changes a proxy’s permissions or basis for access within a clinical system.
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Patient’s identifier (NHS number)</li>
          <li>Proxy’s identifier (NHS number)</li>
          <li>The specific permission or attribute being updated (e.g., granting a proxy access to view a patient’s immunisations)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy’s access is updated to reflect what they can do on behalf of a patient and the basis on which they can do this.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <strong>Patient</strong>
        <ol>
          <li>A patient uses a patient-facing service to change what a proxy can do on their behalf.</li>
          <li>The patient receives confirmation about the proxy’s access being updated.</li>
        </ol>
        <strong>Clinical Professional</strong>
        <ol>
          <li>A clinical professional uses their clinical system to change what a proxy can do on behalf of a patient or the basis on which access is granted (e.g., updating a parent’s access as a child reaches Gillick competence).</li>
          <li>The clinical professional receives confirmation of access being updated.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>An update is attempted on a relationship that does not exist.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>Patient or clinical professional is not sufficiently verified or authenticated.</li>
          <li>Invalid or missing patient identifier.</li>
          <li>Invalid or missing proxy identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>



### Manage what a proxy is allowed to do for a patient

<table class="assets" title="PDS Use Case 6">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> patient,<br>
        <strong>I need</strong> to be able to revoke a proxy’s access to my services,<br>
        <strong>So that</strong> I can ensure access is discontinued when I don’t need it.<br><br>
        
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to revoke a proxy’s access to act on a patient’s behalf,<br>
        <strong>So that</strong> I can ensure access is discontinued if the patient does not need it or if it poses a risk of harm to the patient.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies, Clinical professionals</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>
        Every time a patient revokes a proxy’s access to act on their behalf.<br>
        Every time a clinical professional revokes a proxy’s access to act on behalf of a patient.
      </td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        A patient revokes a proxy’s access within a patient-facing service.<br>
        A clinical professional revokes a proxy’s access to act on behalf of a patient within a clinical system.
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Patient’s identifier (NHS number)</li>
          <li>Proxy’s identifier (NHS number)</li>
          <li>A reason for revocation is provided</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy’s access is revoked, preventing them from acting on behalf of a patient.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <strong>Patient</strong>
        <ol>
          <li>A patient uses a patient-facing service to revoke a proxy’s access to act on their behalf.</li>
          <li>The patient receives confirmation about the proxy’s access being revoked.</li>
        </ol>
        <strong>Clinical Professional</strong>
        <ol>
          <li>A clinical professional uses their clinical system to revoke a proxy’s access to act on behalf of a patient.</li>
          <li>The clinical professional receives confirmation of access being revoked.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>A revocation is attempted on a relationship that does not exist.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>Patient or clinical professional is not sufficiently verified or authenticated.</li>
          <li>Invalid or missing patient identifier.</li>
          <li>Invalid or missing proxy identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>



