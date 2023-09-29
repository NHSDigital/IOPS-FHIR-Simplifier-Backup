## Element: `priority` <span class="mro-circle optional" title="Optional"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: not to be used within an implementation -  or used <strong>with caution</strong>.
</div>

The stating of a priority, in any business context including healthcare, is often de-valued as given the choice, every clinician wants medication urgently for their patients.

The FHIR standard uses a fixed value-set, that cannot be modified, denoting priority in increasing order of magnitude, with `stat` being the highest possible priority, e.g. an emergency.

<table data-responsive>
    <thead>
        <tr>
            <th>Code</th>
            <th>Display</th>
            <th>Definition</th>
        </tr>
    </thead>
    <tbody>
        <!-- routine -->
        <tr>
            <td><code>routine</code></td>
            <td>Routine</td>
            <td>The request has normal priority.</td>
        </tr>
        <!-- urgent -->
        <tr>
            <td><code>urgent</code></td>
            <td>Urgent</td>
            <td>The order should be urgently.</td>
        </tr>
        <!-- stat -->
        <tr>
            <td><code>stat</code></td>
            <td>STAT</td>
            <td>The order is time-critical.</td>
        </tr>
        <!-- asap -->
        <tr>
            <td><code>asap</code></td>
            <td>ASAP</td>
            <td>The order should be acted on as soon as possible.</td>
        </tr>
    </tbody>
</table>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Warning</strong>: FHIR R4 has changed the definition of the request priority. In STU3 is was "<i>The order should be acted on as soon as possible</i>". In R4 it is now "<i>The request should be actioned immediately - highest possible priority. E.g. an emergency.</i>"</strong>
    </div>
</div>

### Usage of the term "STAT"

The <code>STAT</code> request priority is potentially confusing as it has two meanings:

1. to indicate a "<i>here and now</i>" order going to pharmacy
2. used within a <code>dosageInstruction</code> can also mean "<i>give once immediately</i>"

If <code>priority</code> is used, consider only initially supporting the <code>routine</code> and <code>urgent</code> request priorities, and set clear criteria for when a <code>medicationRequest</code> should be marked and handled as <code>urgent</code>.

---