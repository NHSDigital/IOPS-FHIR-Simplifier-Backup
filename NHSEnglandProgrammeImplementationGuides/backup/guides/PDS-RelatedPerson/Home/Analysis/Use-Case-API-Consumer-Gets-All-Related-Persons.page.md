## {{page-title}}

<table class="assets" title="API Consumer gets all related persons">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As the</strong> National Proxy Service,<br>
        <strong>I want</strong> to retrieve all related persons for a specific patient,<br>
        <strong>So that</strong> I can display relationship information for clinical or administrative purposes.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>Proxy, Related Person Network (RPN)</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Multiple times a day.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>API Consumer requests all relationships for a patient.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>API Consumer is authenticated.</li>
          <li>API Consumer is authorised to view relationships.</li>
          <li>Patient NHS number is valid.</li>
          <li>Patient record exists in Neptune.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>All active related persons are returned for the specified patient.</li>
          <li>Relationship provenance information is included for each relationship.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Flow</strong></td>
      <td>
        <ol>
          <li>API Consumer sends GET request to <code>/RelatedPerson?patient:identifier</code> endpoint.</li>
          <li>System validates the request parameters.</li>
          <li>System retrieves all active related persons from the RPN datastore.</li>
          <li>System returns a FHIR Bundle containing RelatedPerson resources.</li>
          <li>Each RelatedPerson resource includes:
            <ul>
              <li>Relationship type (mother, father, etc.).</li>
              <li>NHS Number of the related person if available.</li>
              <li>Name and demographic details.</li>
              <li>Provenance information (source of relationship data).</li>
              <li>Status (active, inactive, etc.).</li>
            </ul>
          </li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>If the patient has more related persons than the default page size:
            <ul>
              <li>Response includes links to retrieve next pages of results.</li>
              <li>API Consumer can follow the links to retrieve all results.</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>If no related persons exist for the patient:
            <ul>
              <li>System returns an empty FHIR Bundle.</li>
            </ul>
          </li>
          <li>If the patient doesn't exist:
            <ul>
              <li>System returns a <code>404 Not Found</code> error.</li>
            </ul>
          </li>
          <li>If the API Consumer does not have the appropriate permissions:
            <ul>
              <li>System returns a <code>403 Forbidden</code> error.</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Acceptance Criteria</strong></td>
      <td>
        <ul>
          <li>System returns all active related persons for the requested patient.</li>
          <li>System handles pagination appropriately for patients with many relationships.</li>
          <li>System includes provenance information for each relationship.</li>
          <li>System correctly indicates the origin of each relationship (GRO, PDS Riak, etc.).</li>
          <li>Only authenticated API Consumers can access the API.</li>
          <li>API Consumers can only access resources within their authorized scopes.</li>
          <li>Authentication tokens expire after an appropriate period.</li>
          <li>API properly enforces scope-based access control.</li>
          <li>API properly supports multiple versions simultaneously.</li>
          <li>API clearly indicates version information in responses.</li>
          <li>API provides an appropriate warning period before version deprecation.</li>
          <li>Documentation clearly explains differences between versions.</li>
          <li>All API errors return appropriate HTTP status codes.</li>
          <li>Error responses follow the FHIR <code>OperationOutcome</code> structure.</li>
          <li>Error messages are clear, actionable, and user-friendly.</li>
          <li>Each error includes a correlation ID for support reference.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
 

