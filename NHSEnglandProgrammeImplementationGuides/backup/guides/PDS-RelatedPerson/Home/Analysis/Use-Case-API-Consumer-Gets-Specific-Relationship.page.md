## {{page-title}}

<table class="assets" title="API Consumer Gets Specific Relationship">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As an</strong> API Consumer (Proxy),<br>
        <strong>I want</strong> to be able to search using a Patient's NHS Number,<br>
        <strong>So that</strong> I can retrieve details of a Patient's relationships including provenance data.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>API Consumer (Proxy)</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Multiple times a day.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>API Consumer requests specific relationships for a patient.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>API Consumer is authenticated.</li>
          <li>API Consumer is authorised to view relationships.</li>
          <li>Relationship ID or patient and related person IDs are provided.</li>
          <li>Relationship exists in the system.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>Detailed information about the specific relationship is returned.</li>
          <li>Complete provenance information is included.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Flow</strong></td>
      <td>
        <ol>
          <li>Proxy receives an online request for Proxy access.</li>
          <li>Proxy sends GET request to <code>/RelatedPerson/id</code> endpoint.</li>
          <li>System validates that the relationship ID exists.</li>
          <li>System retrieves relationship details including:
            <ul>
              <li>Relationship type (mother, father, etc.).</li>
              <li>NHS Numbers of both people.</li>
              <li>Names and demographic details.</li>
              <li>Detailed provenance information.</li>
              <li>Status (active, inactive, etc.).</li>
              <li>Period of validity if applicable.</li>
            </ul>
          </li>
          <li>System returns a complete <code>RelatedPerson</code> FHIR resource.</li>
          <li>Proxy uses information for processing Proxy Access.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>When a unique match is not found for a parent, then the parent is not added as a RelatedPerson on the child's record.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li><strong>Given</strong> that a child's record has a mother or father RelatedPerson with an NHS number,</li>
          <li><strong>When</strong> a parent match is found with a different NHS number,</li>
          <li><strong>Then</strong> the parent matched by RPN is not added to the child's record as a RelatedPerson,</li>
          <li><strong>And</strong> an NBO work item is raised.</li>
          <li>If the relationship doesn't exist:
            <ul>
              <li>System returns a <code>404 Not Found</code> error.</li>
            </ul>
          </li>
          <li>If either person doesn't exist:
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
          <li>System returns detailed information for the requested relationship.</li>
          <li>System includes complete provenance information.</li>
          <li>System provides appropriate error responses when relationships or people don't exist.</li>
          <li>System supports querying by relationship ID or by patient and related person IDs.</li>
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
