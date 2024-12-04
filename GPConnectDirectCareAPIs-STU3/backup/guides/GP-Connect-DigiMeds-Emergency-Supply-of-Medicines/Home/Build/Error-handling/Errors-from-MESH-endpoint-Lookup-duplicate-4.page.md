## {{page-title}}

The following table describes error codes returned from the MESH server as a result of issues encountered using the facility to [route a message automatically to the registered practice](https://simplifier.net/guide/direct-care-messaging-implementation-guide--1-3-1/Home/Authentication/Integration-with-MESH?version=current).

- the following errors, when encountered, MUST be handled gracefully by the message sending system

<table data-responsive data-no-sort>
    <thead>
        <tr>
            <th>Status code</th>
            <th>MESH error code</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <!-- EPL-150 -->
        <tr>
            <td>EPL-150</td>
            <td><code>ERROR_TOO_MANY_MAILBOX_MATCHES</code></td>
            <td>Multiple mailboxes matches</td>
        </tr>
        <!-- EPL-151 -->
        <tr>
            <td>EPL-151</td>
            <td><code>ERROR_NO_MAILBOX_MATCHES</code></td>
            <td>No mailbox matched</td>
        </tr>
        <!-- EPL-152 -->
        <tr>
            <td>EPL-152</td>
            <td><code>ERROR_INVALID_NHSNUMBER</code></td>
            <td>Invalid NHS Number</td>
        </tr>
        <!-- EPL-153 -->
        <tr>
            <td>EPL-153</td>
            <td><code>ERROR_NHSNUMBER_NOT_FOUND</code></td>
            <td>NHS Number not found</td>
        </tr>
        <!-- EPL-154 -->
        <tr>
            <td>EPL-154</td>
            <td><code>ERROR_NO_DEMOGRAPHICS_MATCH</code></td>
            <td>NHS Number supplied does not match the demographics</td>
        </tr>
    </tbody>
</table>

---