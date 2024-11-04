## {{page-title}}

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
