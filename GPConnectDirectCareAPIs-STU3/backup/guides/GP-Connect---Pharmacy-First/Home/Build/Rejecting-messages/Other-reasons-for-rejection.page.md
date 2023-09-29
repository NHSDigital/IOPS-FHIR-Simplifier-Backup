## {{page-title}}

The following are examples of where a message may be rejected by the receiving system.

<table data-responsive class="nhsd-!t-margin-bottom-6 nhsd-!t-margin-top-6">
    <tbody>
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                The patient may not be known by the practice
            </td>
            <td>
                The message could have been routed to the wrong GP practice.
            </td>
        </tr>
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                The patient may have recently moved GP practices, or are part way through transferring
            </td>
            <td>
                The message may have been sent to the old practice, rather than the new one that the patient is now registered at.
            </td>
        </tr>
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                The GP may decide to reject the message upon review as they do not want it in their patient record
            </td>
            <td>
                It's not understood the reasons why a message may be rejected; however, since a task in workflow is being created to 'accept' the incoming message, it is possible that a GP practice could reject it - intentionally, or otherwise. It is advised that in such circumstances, the receiving practice should notify the sending organisation that they have rejected the payload.
            </td>
        </tr>
    </tbody>
</table>