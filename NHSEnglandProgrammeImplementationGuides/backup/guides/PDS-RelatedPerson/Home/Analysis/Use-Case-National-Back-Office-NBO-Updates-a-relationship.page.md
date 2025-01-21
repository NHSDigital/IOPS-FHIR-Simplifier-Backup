## {{page-title}}

<table class="assets" title="NBO Updates a Relationship Use Case">
  <tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td>NBO Updates a Relationship</td>
    </tr>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As an</strong> NBO Demographics Admin,<br>
        <strong>I want</strong> to be able to update relationship data for relationships that originated either from PDS Riak or in Neptune,<br>
        <strong>So that</strong> I can effectively resolve potential Duplication or Confusion cases.
      </td>
    </tr>
    <tr>
      <td><strong>Actors (Role)</strong></td>
      <td>NBO Demographics Admin</td>
    </tr>
    <tr>
      <td><strong>Frequency of Use</strong></td>
      <td>Multiple times a day.</td>
    </tr>
    <tr>
      <td><strong>Triggers</strong></td>
      <td>
        <ul>
          <li>NBO Demographics Admin views a Duplication or Confusion work item (Analysis - NBO Data Quality Items).</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Pre-conditions</strong></td>
      <td>
        <ul>
          <li>A Demographics Admin is authenticated.</li>
          <li>A Demographics Admin is authorised to view a relationship in PDS Riak or Neptune using information from the work item.</li>
          <li>A Demographics Admin has investigated the work item and identified a potential Duplication or Confusion.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>A Demographics Admin will update the relationship based on their current process.</li>
          <li>A Demographics Admin will inform the team and close the work item.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Flow</strong></td>
      <td>
        <ol>
          <li>An NBO Demographics Admin views a relevant work item.</li>
          <li>The Demographics Admin carries out an investigation based on information from the work item.</li>
          <li>The Demographics Admin updates the relationship data as they currently do.</li>
          <li>The Demographics Admin informs the team and closes the work item.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>Where the NBO Demographics Admin cannot retrieve relevant data, they create a new relationship.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Exception</strong></td>
      <td>
        <ul>
          <li>None specified.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
<br>
