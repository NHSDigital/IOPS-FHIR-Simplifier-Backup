## {{page-title}}

The following table describes error codes returned from the MESH server as a result of issues encountered using the facility to route a message automatically to the registered practice.

The following errors, when encountered, MUST be handled gracefully by the message sending system.

<table>
  <thead>
    <tr>
      <th data-no-sort>Status Code</th>
      <th data-no-sort>MESH Error Code</th>
      <th data-no-sort>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>EPL-150</td>
      <td>ERROR_TOO_MANY_MAILBOX_MATCHES</td>
      <td>Multiple mailboxes matches</td>
    </tr>
    <tr>
      <td>EPL-151</td>
      <td>ERROR_NO_MAILBOX_MATCHES</td>
      <td>No mailbox matched</td>
    </tr>
    <tr>
      <td>EPL-152</td>
      <td>ERROR_INVALID_NHSNUMBER</td>
      <td>Invalid NHS Number</td>
    </tr>
    <tr>
      <td>EPL-153</td>
      <td>ERROR_NHSNUMBER_NOT_FOUND</td>
      <td>NHS Number not found</td>
    </tr>
    <tr>
      <td>EPL-154</td>
      <td>ERROR_NO_DEMOGRAPHICS_MATCH</td>
      <td>NHS Number supplied does not match the demographics</td>
    </tr>
  </tbody>
</table>

MESH will generate these errors in the form of error reports which will be placed in the sender’s mailbox to await collection and processing by the sending organisation.

---