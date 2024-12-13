## {{page-title}}

### Proxy Revocation

<table class="assets" title="Proxy Revocation Use Case">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to be able to revoke a proxy relationship where I deem necessary,<br>
        <strong>So that</strong> access remains safe and appropriate.<br><br>
        
        <strong>As a</strong> patient with capacity,<br>
        <strong>I need</strong> to be able to revoke a proxy’s access to my records and services,<br>
        <strong>So that</strong> I am empowered to take decisions about who is permitted to access services and make healthcare decisions on my behalf.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies, Patients, Clinical professional / General practitioner</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Whenever there is a change in circumstances that affects a patient’s wishes or the safety/appropriateness of the relationship.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>Trigger 1: A clinical professional revokes access using a clinical system.</li>
          <li>Trigger 2: A patient revokes proxy access using a patient-facing service.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>An authorised relationship exists in the National Proxy Service between a given proxy and patient.</li>
          <li>The patient or clinical professional has determined that the proxy relationship should no longer be in place.</li>
          <li>Trigger 1: The clinical professional has authenticated in their clinical system.</li>
          <li>Trigger 2: The patient has authenticated with a patient-facing service that supports proxy revocation.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy relationship has been revoked and can no longer be used for accessing services.</li>
          <li>A reason for revocation has been recorded for audit purposes.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <strong>Trigger 1:</strong>
        <ol>
          <li>A clinical professional has determined that access to a patient’s services is no longer safe or appropriate for a given proxy.</li>
          <li>The clinical professional queries their clinical system to identify the proxy relationship in question.</li>
          <li>The clinical professional revokes the proxy relationship.</li>
        </ol>
        <strong>Trigger 2:</strong>
        <ol>
          <li>A patient has determined that they no longer wish a given proxy to be able to access services on their behalf.</li>
          <li>The patient uses the patient-facing service to identify the proxy relationship in question.</li>
          <li>The patient revokes the proxy relationship.</li>
          <li>A confirmation notification is sent to the patient.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>The removal or amendment of individual permissions in a clinical system is outside the scope of this use case and is a local concern. Revocation should result in unilateral removal of access.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        Patient is not sufficiently verified or authenticated.
      </td>
    </tr>
  </tbody>
</table>
<br>
