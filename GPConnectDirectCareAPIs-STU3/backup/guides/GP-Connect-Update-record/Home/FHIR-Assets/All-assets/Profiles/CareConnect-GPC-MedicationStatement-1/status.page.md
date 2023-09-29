## {{page-title}}

<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">

It provides the consumer with information to determine if the medication is relevant for their use case.

For example: whether the medication deemed 'current' (or <code>active</code>).

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>Status</th>
            <th data-no-sort>FHIR Definition</th>
            <th data-no-sort>Recommendation</th>
        </tr>
    </thead>
    <tbody>
        <!-- active -->
        <tr>
            <td><code>active</code></td>
            <td>
                The medication is still being taken.
            </td>
            <td>
                It is believed the medication is active in the patients system.
            </td>
        </tr>
        <!-- completed -->
        <tr>
            <td><code>completed</code></td>
            <td>
            	The medication is no longer being taken.
            </td>
            <td>
                A course of medication has been completed and the medication is not active in the patients system.
            </td>
        </tr>
        <!-- entered-in-error -->
        <tr>
            <td><code>entered-in-error</code></td>
            <td>
                The statement was recorded incorrectly.
            </td>
            <td>
                Indicates the <code>MedicationStatement</code> is INVALID. It is not expected that a <code>MedicationStatement</code> with this status to be included in exchanges.
            </td>
        </tr>
        <!-- intended -->
        <tr>
            <td><code>intended</code></td>
            <td>
                The medication may be taken at some time in the future.
            </td>
            <td>
                It is intended that the medication will be given to the patient. When this is used <code>effective[x]</code> MUST indicate when it is intended that the medication to be taken.
            </td>
        </tr>
        <!-- stopped -->
        <tr>
            <td><code>stopped</code></td>
            <td>
                Actions implied by the statement have been permanently halted, before all of them occurred.
            </td>
            <td>
                Medication has been stopped before the completion of the prescribed course and there is no plan to restart it. When used the reason MUST be indicated in <code>statusReason</code>.
            </td>
        </tr>
        <!-- on-hold -->
        <tr>
            <td><code>on-hold</code></td>
            <td>
                Actions implied by the statement have been temporarily halted, but are expected to continue later. May also be called "suspended".
            </td>
            <td>
                Medication has been temporarily stopped.
                <br />
                When used the reason MUST be indicated in <code>statusReason</code>.
                <br />
                Where it is known when it is indented to restart it this may be indicated in <code>statusReason</code>.
            </td>
        </tr>
        <!-- unknown -->
        <tr>
            <td><code>unknown</code></td>
            <td>
                <i>Not implemented within STU3</i>
            </td>
            <td>
                The patient may have had some encounter with this medication, but the current status is unknown. It is not expected that this status be avoided.
            </td>
        </tr>
        <!-- not-taken -->
        <tr>
            <td><code>not-taken</code></td>
            <td>
                <i>Not implemented within STU3</i>
            </td>
            <td>
                The patient has not taken the medication as prescribed.
            </td>
        </tr>        
    </tbody>
</table>
