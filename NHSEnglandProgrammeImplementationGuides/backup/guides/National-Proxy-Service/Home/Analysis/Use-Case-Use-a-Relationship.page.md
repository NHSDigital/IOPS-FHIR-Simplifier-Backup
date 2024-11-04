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
