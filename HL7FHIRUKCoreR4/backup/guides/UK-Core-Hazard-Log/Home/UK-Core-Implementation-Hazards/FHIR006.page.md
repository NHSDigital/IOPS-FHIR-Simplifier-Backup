## {{page-title}}

## Ambiguity in negated (drug allergy) codes 

<div class="row">
  <div class="column">
  <h2>Initial Risk Rating</h2>
  <table class="assets">
      <tr>
        <th>Likelihood</th>
        <th>Consequence</th>
        <th>Risk</th>
      </tr>
      <tr>
        <td>Medium</td>
        <td>Considerable</td>
          <td class="risk3">3</td>
        </tr>
    </table>
  </div>
  <div class="column">
  <H2>Residual Hazard Risk Rating</H2>
<table class="assets">
      <tr>
        <th>Likelihood</th>
        <th>Consequence</th>
        <th>Risk</th>
      </tr>
      <tr>
        <td>Low</td>
        <td>Considerable</td>
        <td class="risk2">2</td>
      </tr>
    </table>
  </div>
</div>



## Hazard Description
FHIR allows negation in codeable concepts. It is possible to include negation statements that apply at the level of the whole list and it is also possible to have separate lists for thing like medication allergies.
Adding new Allergy Intolerances to the list can cause confusion that any negation statements that are voided by the addition of a new record are/are not removed from the list.
For e.g. if the list contains a <code>no known food allergies</code> record and a user/system add an <code>intolerance to grape flavour</code> record, then users/systems might/might not remove the <code>no known food allergies</code> record.

## Potential Clinical Impact
1. Incorrect medications may be given based on incomplete clinical information leading to potential delay in care.
2. Incorrect medication dispensed to patient which can lead to severe consequences to patient health.

## Possible Causes
A variety of negated allergy codes options that are available which clinicians can choose.

## Existing Controls
Users/systems may differentiate between affirmatively stating that a patient has no known allergies versus either not including allergies in the record; or asserting that allergies were not reviewed and are unknown.

## Design
1. Prior to adding new allergy/intolerance, a list of existing negated and refuted reactions should be reviewed and reconciled.
2. Negated codes, if stripped out, must not be sent if there are positive codes.
3. Send everything except negative codes.
4. Text should reflect actual meaning of the allergy codes - representing the real meaning of the code.
5. The sending party to ensure that communication is well formed.

## Test
Clinical validation assurance testing to cover negated codes.

## Training
Relevant training materials to be produced/updated by suppliers of secondary and primary care to cover the various available negated codes.

## Business Process Change
n/a
