## `status` (Mandatory)

**MUST** be populated with a fixed valueset defined within the FHIR standard.

**It is expected that most implementations will require the use of status to support workflow.**

The status can be used to determine the overall status of medication administration events.

It is recommended that the `status` is used to indicate the status at a high-level so that integrated systems can determine how to represent this information.

<table id="assets">
    <thead>
        <tr>
            <th>Status</th>
            <th>FHIR Definition</th>
            <th>Implementation Guidance</th>
        </tr>
    </thead>
    <tbody>
        <!-- in-progress -->
        <tr>
            <td><code>in-progress</code></td>
            <td>
                The administration has started but has not yet completed.
            </td>
            <td>
            </td>
        </tr>
        <!-- not-done -->
        <tr>
            <td><code>not-done</code></td>
            <td>
                The administration was terminated prior to any impact on the subject (though preparatory actions may have been taken)
            </td>
            <td>
            </td>
        </tr>
        <!-- on-hold -->
        <tr>
            <td><code>on-hold</code></td>
            <td>
                Actions implied by the administration have been temporarily halted, but are expected to continue later. May also be called 'suspended'.
            </td>
            <td>
            </td>
        </tr>
        <!-- completed -->
        <tr>
            <td><code>completed</code></td>
            <td>
                All actions that are implied by the administration have occurred.
            </td>
            <td>
                This would be a suitable trigger to share the medication administration event with shared records.
            </td>
        </tr>
        <!-- entered-in-error -->
        <tr>
            <td><code>entered-in-error</code></td>
            <td>
                The administration was entered in error and therefore nullified.
            </td>
            <td>
            </td>
        </tr>
        <!-- stopped -->
        <tr>
            <td><code>stopped</code></td>
            <td>
                Actions implied by the administration have been permanently halted, before all of them occurred.
            </td>
            <td>
                A <code>statusReason</code> should be populated with a coded reason for stopping the medication administration.
            </td>
        </tr>
        <!-- unknown -->
        <tr>
            <td><code>unknown</code></td>
            <td>
                The authoring system does not know which of the status values currently applies for this request. Note: This concept is not to be used for 'other' - one of the listed statuses is presumed to apply, it's just not known which one.
            </td>
            <td>
                The patient may have had some encounter with this medication, but the current status is unknown. Avoid the use of this status value where possible.
            </td>
        </tr>    
    </tbody>
</table>

---
<!--
Comments from the Meds Interop Working Group (20-Sept-21).
Whis is "planned' not in this value set?
-->