## {{page-title}}

## Transcription error

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
Receiving systems is unable to process the SNOMED CT code and degrades this to text.

## Potential Clinical Impact
Wrong medication or clinical information is entered manually (in error) in the clinical system by user.

## Possible Causes
The receiving system is only able to process a subset of SNOMED CT codes.

## Existing Controls
Implementation guidance to deprecate to text.

## Design
Implementation guidance to be issued with the FHIR release identifying this possible receiving system risk and alerts for users.

## Test
n/a

## Training
Existing end user local training to use system.

## Business Process Change
n/a
