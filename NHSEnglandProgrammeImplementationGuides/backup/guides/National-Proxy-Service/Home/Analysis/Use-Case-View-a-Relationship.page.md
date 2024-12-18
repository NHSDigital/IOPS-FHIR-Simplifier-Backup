## {{page-title}}

### View proxy relationship(s) for a specific patient or proxy

<table class="assets" title="View Proxy Relationships Use Case">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> patient,<br>
        <strong>I need</strong> to know who my authorised proxies are,<br>
        <strong>So that</strong> I can manage who can act on my behalf.<br><br>
        
        <strong>As a</strong> proxy,<br>
        <strong>I need</strong> to know who I am authorised to act on behalf of,<br>
        <strong>So that</strong> I can assist them with their care.<br><br>
        
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to know the proxies that can act on behalf of a patient,<br>
        <strong>So that</strong> I can manage their access and the patient’s record appropriately.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Patients, Proxies, Clinical professionals</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>
        <ul>
          <li>Whenever a patient seeks to view or manage who can act on their behalf.</li>
          <li>Whenever a proxy seeks to use digital services on behalf of a patient they care for.</li>
          <li>As needed to perform a clinical professional’s duty of care.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>A patient uses a patient-facing service to view or manage their proxies.</li>
          <li>A proxy uses a patient-facing service to use digital services on behalf of a patient they care for.</li>
          <li>A clinical professional uses their local system as part of a care interaction or managing the patient record.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Patient is registered at a GP practice.</li>
          <li>Proxy is registered at a GP practice.</li>
          <li>Proxy relationship is established.</li>
          <li>The patient, proxy, or clinical professional has been authenticated with the system they are using.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The patient can view the proxies that can act on their behalf, and the services they can access for them, in a patient-facing service.</li>
          <li>The proxy can view the patients they can proxy for in a patient-facing service and subsequently use digital services on their behalf.</li>
          <li>The clinical professional can see what services each proxy is permitted to access on behalf of a given patient in their clinical system.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <ol>
          <li>A verified patient, proxy, or clinical professional views the established proxy relationships within a patient-facing service or clinical system.</li>
          <li>The patient-facing service or clinical system displays the proxies that can act on behalf of a given patient (for patients and clinicians) and the patients the proxy is authorised to support with their care (for proxies).</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>If the patient has no proxies that can act on their behalf, then the patient-facing service or clinical system will show that no relationships exist.</td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>    
      Patient, proxy, or clinical professional is not sufficiently verified or authenticated.
      </td>
    </tr>
  </tbody>
</table>
<br>

### Workflow
{{render:View Relationship jpeg.jpg}}

Note: This process remains the same for a patient that needs to know who their authorised proxies are and a clinical professional that needs to know the proxies that can act on behalf of a patient
