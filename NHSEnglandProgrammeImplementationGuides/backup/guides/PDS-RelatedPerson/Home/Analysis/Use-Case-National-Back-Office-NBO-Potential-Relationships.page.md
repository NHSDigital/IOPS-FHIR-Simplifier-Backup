## {{page-title}}

<table class="assets" title="NBO Potential Relationships Use Case">
  <tbody>
    <tr>
      <td><strong>User Story Summary (Clinical Overview)</strong></td>
      <td>
        <strong>As an</strong> NBO Demographics Administrator,<br>
        <strong>I want</strong> to have a clear view of potential relationships,<br>
        <strong>So that</strong> I can more efficiently cross trace information to resolve a duplication or confusion work item.
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
          <li>A Demographics Admin is authorised to view potential relationships.</li>
          <li>A relevant work item is raised.</li>
          <li>A patient referenced on the work item has potential relationships.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Post-conditions</strong></td>
      <td>
        <ul>
          <li>A Demographics Admin uses the potential relationship data to either:
            <ul>
              <li>Merge two records (Duplicate).</li>
              <li>Remove incorrect details from a record (Confusion).</li>
              <li>Delete a record and create a new one (Confusion in rare cases).</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td><strong>Main Flow</strong></td>
      <td>
        <ol>
          <li>An NBO Demographics Admin views a relevant work item.</li>
          <li>Potential relationships can be viewed by the Demographics Admin.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><strong>Alternate Flow</strong></td>
      <td>
        <ul>
          <li>Where no potential relationships are found, none are presented.</li>
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

