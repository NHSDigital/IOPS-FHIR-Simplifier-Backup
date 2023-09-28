## {{page-title}}
## Receiving systems automatically processes medication information

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
        <td>Low</td>
        <td>Major</td>
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
        <td>Very Low</td>
        <td>Major</td>
        <td class="risk2">2</td>
      </tr>
    </table>
  </div>
</div>

 

## Hazard Description
Prescription is incorrect and not as the Prescriber intended. 

## Potential Clinical Impact
Incorrect medication dispensed to patient which can lead to severe consequences to patient health.  

## Possible Causes
1. Incorrect mapping.
2. System design prescriber preference.
3. A dose based medication item from secondary care may be converted to the wrong product based medication item in primary care either as a result of human transcription error or as a result of automated / semi-automated conversion.

## Existing Controls
Pharmacists may act as a control but may not be able to translate the text into meaningful data and recover the problem.

## Design
Human readable rendition of original dose based prescription preserved and presented to primary care prescriber to facilitate cross check. 

## Test
Clinical validation assurance testing to cover all prescribing formats.

## Training
Relevant training materials to be produced/updated by suppliers of secondary and primary care to cover the various prescribing formats.

## Business Process Change
All clinicians should review medication message content before accepting into their systems.
