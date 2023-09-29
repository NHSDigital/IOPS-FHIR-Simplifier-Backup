## Element: `status` <span class="mro-circle mandatory" title="Mandatory"></span>

When used it must be populated with a fixed valueset defined within the FHIR standard.

**It is expected that most implementations will require the use of status to support workflow.**

The scope of `status` may vary depending on the nature of the implementation. The FHIR standard defines the `status` of `Completed` as “All actions that are implied by the prescription have occurred”. 

This allows for different design decisions for tracking a medication request status.

- An implementation may track the `status` through to the receipt of the medication request at the pharmacy, after which the `status` is `Completed`

- An implementation may track the `status` through to completion of dispensing events, after which the `status` is `Completed`

- An implementation may track the `status` through to completion of administration events for the medication that has been dispensed, after which the `status` is `Completed`.


The following guidance is based on an implementation tracking the status through to completion of dispensing events.

<table data-responsive>
    <thead>
        <tr>
            <th>Status</th>
            <th>FHIR Definition</th>
            <th>Recommendation</th>
        </tr>
    </thead>
    <tbody>
        <!-- Draft -->
        <tr>
            <td><code>Draft</code></td>
            <td>
            	The prescription is not yet "actionable", e.g. it is a work in progress, requires sign-off, verification or needs to be run through decision support process.
            </td>
            <td>
                The order is work in progress within the ePMA system and has not yet sent to the pharmacy.
            </td>
        </tr>
        <!-- Active -->
        <tr>
            <td><code>Active</code></td>
            <td>
                The prescription is "actionable", but not all actions that are implied by it have occurred yet.
            </td>
            <td>
                The order has been sent and accepted by the pharmacy. Dispensing and administration activities may of started but are not yet `Complete`.
            </td>
        </tr>
        <!-- Completed -->
        <tr>
            <td><code>Completed</code></td>
            <td>
                All actions that are implied by the prescription have occurred yet.
            </td>
            <td>
                Dispensing activities have been completed for the medication defined within the order.
            </td>
        </tr>
        <!-- On hold -->
        <tr>
            <td><code>On-Hold</code></td>
            <td>
                Actions implied by the prescription are to be temporarily halted, but are expected to continue later. May also be called `Suspended`.
            </td>
            <td>
                Will prevent the order being sent to the pharmacy. If already sent, an update needs to be sent to the pharmacy to temporarily halt further dispensing.
            </td>
        </tr>
        <!-- Cancelled -->
        <tr>
            <td><code>Cancelled</code></td>
            <td>
                The prescription has been withdrawn before any administrations have occurred.
            </td>
            <td>
                Will prevent the order being sent to the pharmacy. If already sent, an update needs to be sent to the pharmacy so that no further medication is dispensed.
            </td>
        </tr>
        <!-- Stopped -->
        <tr>
            <td><code>Stopped</code></td>
            <td>
                Actions implied by the prescription are to be permanently halted, before all of the administrations occurred. This should not be used if the original order was entered in error.
            </td>
            <td>
                The order needs to be stopped on clinical grounds. An update needs to be sent to the pharmacy so that no further medication is dispensed.
            </td>
        </tr>
        <!-- Entered in Error -->
        <tr>
            <td><code>Entered in Error</code></td>
            <td>
                Some of the actions that are implied by the medication request may have occurred. For example, the medication may have been dispensed and the patient may have taken some of the medication. Clinical decision support systems should take this status into account.
            </td>
            <td>
                The order needs to be stopped due to human data entry error. An update needs to be sent to the pharmacy so that no further medication is dispensed.
            </td>
        </tr>
        <!-- Unknown -->
        <tr>
            <td><code>Unknown</code></td>
            <td>
                The authoring/source system does not know which of the status values currently applies for this observation. Note: This concept is not to be used for ‘other’ - one of the listed statuses is presumed to apply, but the authoring/source system does not know which.
            </td>
            <td>
                <strong>Recommended not to be supported</strong> as the use case for this status value is unclear.
            </td>
        </tr>
        
    </tbody>
</table>

### Logical `medicationRequest` status transitions

This state transition diagram is an enhancement over the generic [State Machine](https://www.hl7.org/fhir/request.html#statemachine) defined within the FHIR specification. It includes the status values associated with a medication request with transitions applicable to a UK implementation.

<br />

{{render: medication-request-status-flow }}{: .img-responsive }

<br />

### Status transitions explained

<table data-responsive>
    <thead>
        <tr>
            <th>Previous</th>
            <th>Future</th>
            <th>Interoperability Recommendation</th>
        </tr>
    </thead>
    <tbody>
        <!-- Draft to Active -->
        <tr>
            <td><code>Draft</code></td>
            <td><code>Active</code></td>
            <td>
                This transition will trigger the sending / sharing of the MedicationRequest from the ePMA system to the pharmacy system to start dispensing activities. Within a RESTful implementation this would be typically implemented as an <code>HTTP POST</code>.
            </td>
        </tr>
        <!-- Draft to Cancelled -->
        <tr>
            <td><code>Draft</code></td>
            <td><code>Cancelled</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- Draft to On-hold -->
        <tr>
            <td><code>Draft</code></td>
            <td><code>On-Hold</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- Draft to Entered-in-Error -->
        <tr>
            <td><code>Draft</code></td>
            <td><code>Entered-in-Error</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- On-hold to Draft -->
        <tr>
            <td><code>On-Hold</code></td>
            <td><code>Draft</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- On-hold to Active -->
        <tr>
            <td><code>On-Hold</code></td>
            <td><code>Active</code></td>
            <td>
                This transition will trigger an update to the <code>MedicationRequest</code> from the ePMA system to the pharmacy system to restart dispensing activities. Within a RESTful implementation this would be typically implemented as either an <code>HTTP PUT</code> or <code>HTTP PATCH</code>.
            </td>
        </tr>
        <!-- On-hold to Canelled -->
        <tr>
            <td><code>On-Hold</code></td>
            <td><code>Active</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- On-hold to Stopped -->
        <tr>
            <td><code>On-Hold</code></td>
            <td><code>Stopped</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- On-hold to Entered-in-error -->
        <tr>
            <td><code>On-Hold</code></td>
            <td><code>Entered-in-error</code></td>
            <td>
                Contained within the ePMA system.
            </td>
        </tr>
        <!-- Active to Active -->
        <tr>
            <td><code>Active</code></td>
            <td><code>Active</code></td>
            <td>
                Not a MedicationRequest status transition but the pharmacy system could send / share dispensing activities with the ePMA system, typically using a FHIR profile based on <code>MedicationDispense</code>. Within a RESTful implementation this would be typically implemented as an <code>HTTP POST</code>.
            </td>
        </tr>
        <!-- Active to On-hold -->
        <tr>
            <td><code>Active</code></td>
            <td><code>On-Hold</code></td>
            <td>
                This transition will trigger an update to the <code>MedicationRequest</code> from the ePMA system to the pharmacy system to suspend dispensing activities. Within a RESTful implementation this would be typically implemented as either an <code>HTTP PUT</code> or <code>PATCH</code>.
                <br />
                <br />
                If dispensing has already occurred but meds have not been delivered to the ward then they can stay within the pharmacy until the request is re-activated. If meds have been delivered to the ward then there is no action required by the pharmacy system.
            </td>
        </tr>
        <!-- Active to Entered-in-Error -->
        <tr>
            <td><code>Active</code></td>
            <td><code>Entered-in-Error</code></td>
            <td>
                This transition will trigger an update to the <code>MedicationRequest</code> from the ePMA system to the pharmacy system to stop dispensing activities. Within a RESTful implementation this would be typically implemented as either an <code>HTTP PUT</code> or <code>PATCH</code>.
            </td>
        </tr>
        <!-- Active to Stopped -->
        <tr>
            <td><code>Active</code></td>
            <td><code>Stopped</code></td>
            <td>
                This transition will trigger an update to the <code>MedicationRequest</code> from the ePMA system to the pharmacy system to stop dispensing activities. Within a RESTful implementation this would be typically implemented as either an <code>HTTP PUT</code> or <code>PATCH</code>.
            </td>
        </tr>
        <!-- Active to Completed -->
        <tr>
            <td><code>Active</code></td>
            <td><code>Completed</code></td>
            <td>
                Contained within the ePMA system. All requested medication has been received from pharmacy and has been recorded / confirmed within the ePMA system.
            </td>
        </tr>
    </tbody>
</table>

---