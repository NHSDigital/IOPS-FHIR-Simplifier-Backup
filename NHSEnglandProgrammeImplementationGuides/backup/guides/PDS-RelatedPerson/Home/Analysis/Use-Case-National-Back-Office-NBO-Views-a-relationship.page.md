## {{page-title}}

<table class="assets" title="NBO Views a Relationship Use Case">
  <tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td>NBO Views a Relationship</td>
    </tr>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As an</strong> NBO Demographics Admin,<br>
        <strong>I want</strong> to have a clear view of a relationship that either originated from PDS Riak or in Neptune,<br>
        <strong>So that</strong> I can effectively investigate Potential Duplication or Confusion.
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
          <li>A Demographics Admin will input the following information:
            <ul>
              <li>NHS Number for parents.</li>
              <li>Forename(s), Surname (family name).</li>
              <li>Date of Birth.</li>
              <li>Gender.</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>A successfully matched information is retrieved.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Flow</strong></td>
      <td>
        <ol>
          <li>An NBO Demographics Admin views a relevant work item.</li>
          <li>The Demographics Admin inputs the work item details and retrieves relevant data.</li>
          <li>The Demographics Admin carries out an investigation based on the information retrieved from the work item.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>Where the NBO Demographics Admin cannot retrieve relevant data, the relationship information is unavailable.</li>
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
