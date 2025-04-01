## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important</strong>: This is the next most important element of a <code>MedicationStatement</code> after the <code>Medication</code>.
</div>

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

### Statuses expanded

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important</strong>: Determining the value of this element when constructing the resource.
</div>

The status will need to be calculated if the `basedOn` or `partOf` elements within the profile are defined.

A `MedicationStatement` represents a snapshot in time of a patient medication - and if the status has not been provided, then the following business rule may apply to compute the state.

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>Status</th>
            <th data-no-sort>How it can be determined</th>
        </tr>
    </thead>
    <tbody>
        <!-- active -->
        <tr>
            <td><code>active</code></td>
            <td>
                <ul>
                    <li>
                        A completed <code>MedicationRequest</code> (if known) where the current date is between the <code>dispenseRequest.validityPeriod</code> element. The <code>MedicationStatement.effectivePeriod</code> element should reflect this information.
                    </li>
                    <li>
                        Where the current date is between the <code>MedicationStatement.effectivePeriod</code>
                    </li>
                </ul>
            </td>
        </tr>
        <!-- completed -->
        <tr>
            <td><code>completed</code></td>
            <td>
                <ul>
                    <li>
                        Where the current date is after the <code>MedicationStatement.effectivePeriod</code>
                    </li>
                    <li>
                        A completed <code>MedicationRequest</code> (if known) where the <code>dispenseRequest</code> element is either not defined, or the current date is greater than the <code>dispenseRequest.validityPeriod</code>.
                    </li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

<h5><ins>Example</ins></h5>


```xml
<status value="active" />
```

---