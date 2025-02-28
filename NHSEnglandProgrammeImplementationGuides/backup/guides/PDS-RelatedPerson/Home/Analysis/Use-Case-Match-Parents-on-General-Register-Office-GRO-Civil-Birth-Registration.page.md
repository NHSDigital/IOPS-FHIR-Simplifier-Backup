## {{page-title}}

<table class="assets" title="NameMatch Parents on GRO Civil Birth Registration Use Case">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As the</strong> Related Person Network,<br>
        <strong>I want</strong> to create child-parent RelatedPersons from GRO Civil Birth Registrations,<br>
        <strong>So that</strong> more child-parent RelatedPersons are available to API consumers.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>ONS, DPS, RPN</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Weekly (Batch for historic load).</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>Weekly Birth Registration Batch sent via MESH from ONS.</li>
          <li>Historic Birth Registration data stored in DPS.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>Civil Birth Registration has the following fields:
            <ul>
              <li>Parent surnames (Mother and Second Parent).</li>
              <li>Parent DOBs (Mother and Second Parent).</li>
              <li>Parent gender (Mother and Second Parent).</li>
              <li>Parent forenames (Mother and Second Parent).</li>
              <li>Mother postcode.</li>
              <li>Mother’s maiden name.</li>
            </ul>
          </li>
          <li>Child’s NHS number.</li>
          <li>Child’s postcodes.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>A successfully matched RelatedPerson is available on the API.</li>
          <li>Provenance indicates the source of the data.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Flow</strong></td>
      <td>
        <ol>
          <li>GRO Civil Birth Registration data is sent to the Related Person Network in a batch.</li>
          <li>For each Birth Registration:
            <ol>
              <li>A search against the mother data is completed.</li>
              <li>A search against the second parent data is completed.</li>
              <li>Matched parents are persisted as RelatedPersons in the Related Person Network.</li>
              <li>Provenance resource is created for the relationship in the Related Person Network</li>
            </ol>
          </li>
          <li>Provenance indicates the source of the data.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>When a unique match is not found for a parent, then the parent is not added as a RelatedPerson on the child’s record.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>Given that a child’s record has a mother or father RelatedPerson with an NHS number:</li>
          <li>When a parent match is found with a different NHS number:</li>
          <ul>
            <li>The parent matched by RPN is not added to the child’s record as a RelatedPerson.</li>
            <li>An NBO work item is raised.</li>
          </ul>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>
