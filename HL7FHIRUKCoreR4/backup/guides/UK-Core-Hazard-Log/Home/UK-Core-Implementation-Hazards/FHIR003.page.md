## {{page-title}}

## Human readable narrative text might not match the structured or unstructured data

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
Data could be sent as coded data rather than text. If coded information is carried without associated text it may not be
comprehensible in the Transfer of Care discharge summaries.

## Potential Clinical Impact
Patients may receive incorrect diagnosis or treatment.

## Possible Causes
Sending system or receiving systems transform of FHIR message is not correct. 

## Existing Controls
The FHIR standards implementation assumes that narrative text should match the structured and unstructured data. 

## Design
1. Include associated text with any coded field.
2. SNOMED CT is the only coded data that can be carried in outpatient letter communications (e.g. not READ, OPCS, etc).

## Test
This is tested in solution assurance by development of a renderer and messages are clinically assured. This is tested at each implementation site before going live. 

## Training
Implementers to provide guidance on any issue/risk might arise in use or misuse of their products.

## Business Process Change
n/a
