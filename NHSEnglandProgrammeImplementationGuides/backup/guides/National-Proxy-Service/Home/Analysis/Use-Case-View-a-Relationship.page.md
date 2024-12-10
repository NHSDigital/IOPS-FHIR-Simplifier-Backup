## {{page-title}}

### View the patient(s) a proxy can act on behalf of

<table class="assets" title="PDS Use Case 2">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As a</strong> proxy,<br>
        <strong>I need</strong> to know the patients I can act on behalf of,<br>
        <strong>So that</strong> I can access health and care services for them to support them with their care.<br><br>
        <strong>As a</strong> clinical professional,<br>
        <strong>I need</strong> to know the patients that a proxy can act on behalf of and the relationship type,<br>
        <strong>So that</strong> I can manage what they can do on behalf of patients.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxies, Clinical professionals</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>
        Every time a proxy views the patients they can act on behalf of.<br>
        Every time a clinical professional views the patients a proxy can act on behalf of.
      </td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        A proxy views the patients they can act on behalf of within a patient-facing service.<br>
        A clinical professional views the patient(s) a proxy can act on behalf of within their clinical system.
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Proxy’s identifier (NHS number)</li>
          <li>Patient’s identifier (NHS number) – if querying for a specific patient</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>The proxy can view the patients they can act on behalf of, the nature of their relationship to them, and the services they can access for each patient, in a patient-facing service.</li>
          <li>The clinical professional can see the patients the proxy can act on behalf of, the nature of their relationship to them, and the services they can access for each patient, in their clinical system.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Course</strong></td>
      <td>
        <ol>
          <li>A verified proxy or clinical professional views patients that the proxy can act on behalf of within a patient-facing service or clinical system.</li>
          <li>The patient-facing service or clinical system displays the patient(s) that the proxy can act on behalf of, and the services the proxy can access for each patient.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Course</strong></td>
      <td>
        <ul>
          <li>If the patient identifier entered has no existing proxy relationship, an error message is returned.</li>
          <li>If a patient identifier is entered, then if that patient is a proxy, the patient details will be returned.</li>
          <li>If the proxy has no patients they can act on behalf of, then the patient-facing service or clinical system will show that no relationships exist.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>Proxy or clinical professional is not sufficiently verified or authenticated.</li>
          <li>Invalid or missing proxy identifier.</li>
          <li>Invalid or missing patient identifier.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>
