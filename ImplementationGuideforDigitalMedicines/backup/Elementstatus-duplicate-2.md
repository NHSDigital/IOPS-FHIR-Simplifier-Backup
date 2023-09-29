## Element: `status` <span class="mro-circle mandatory" title="Mandatory"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important:</strong> the cardinality of <code>status</code> has been changed from <code>0..1</code> in <code>STU3</code> to <code>1..1</code> in <code>R4</code>.
</div>

When used it must be populated with a fixed valueset defined within the FHIR standard.

**It is expected that most implementations will require the use of status to support workflow.**

### Can the status be used in place of prescription tracking software?

The status can be used to determine the overall status of dispense request; however, it does not cater for the granularity that prescription tracking software can offer.

It is recommended that the `MedicationDispenseStatus` is used to indicate the status at a high-level so that integrated systems can determine how to represent this information.

<table data-responsive>
    <thead>
        <tr>
            <th>Status</th>
            <th>FHIR Definition</th>
            <th>Recommendation</th>
        </tr>
    </thead>
    <tbody>
        <!-- preparation -->
        <tr>
            <td><code>preparation</code></td>
            <td>
            	The core event has not started yet, but some staging activities have begun (e.g. initial compounding or packaging of medication). Preparation stages may be tracked for billing purposes.
            </td>
            <td>
                Exposing this status could be beneficial to the requesting system to indicate the current status of the dispensing activity, if the architecture of the dispensing system allows other systems to query for medication dispense records.
                <br />
                <br />
                <strong>Note:</strong> Consider how the status <code>preparation</code> is presented to the end-user to avoid confusion with <code>in-progress</code>.
            </td>
        </tr>
        <!-- in-progress -->
        <tr>
            <td><code>in-progress</code></td>
            <td>
                The dispense has started but has not yet completed.
            </td>
            <td>
                Exposing this status could be beneficial to the requesting system to indicate the current status of the dispensing activity, if the architecture of the dispensing system allows other systems to query for medication dispense records.
            </td>
        </tr>
        <!-- on-hold -->
        <tr>
            <td><code>on-hold</code></td>
            <td>
                Actions implied by the administration have been temporarily halted, but are expected to continue later. May also be called "suspended"
            </td>
            <td>
                Exposing this status could be beneficial to the requesting system to indicate the current status of the dispensing activity, if the architecture of the dispensing system allows other systems to query for medication dispense records.
            </td>
        </tr>
        <!-- completed -->
        <tr>
            <td><code>completed</code></td>
            <td>
                All actions that are implied by the dispense have occurred.
            </td>
            <td>
                <strong>Recommended for MVP</strong>
                <br />
                This would be a suitable trigger to post / share the medication dispense with the requesting ePMA system.
            </td>
        </tr>
        <!-- entered-in-error -->
        <tr>
            <td><code>entered-in-error</code></td>
            <td>
                The dispense was entered in error and therefore nullified.
            </td>
            <td>
                Not to be used unless specific use-cases can be identified.
            </td>
        </tr>
        <!-- stopped -->
        <tr>
            <td><code>stopped</code></td>
            <td>
                Actions implied by the dispense have been permanently halted, before all of them occurred.
            </td>
            <td>
                <strong>Recommended for MVP</strong>
                <br />
                This would be a suitable trigger to post / share the medication dispense with the requesting ePMA system.
            </td>
        </tr>
    </tbody>
</table>

<br />

{{render: medication-dispense-status-flow }}{: .img-responsive }

---