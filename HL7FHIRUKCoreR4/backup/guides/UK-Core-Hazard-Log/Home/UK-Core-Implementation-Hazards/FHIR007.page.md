## {{page-title}}

## M&A (Linked to risk id FHIR009 - Transcription error)

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
        <td>High</td>
          <td>Major</td>
          <td class="risk4">4</td>
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
Inconsistencies in the way Coded/Uncoded/Local Coded Allergies are recorded.

## Potential Clinical Impact
The way Allergies are currently coded in GP Clinical Systems is not standard. Different suppliers use different coding systems some of which are proprietary to that particular system (EMIS).
<br>
There is a SNOMED CT subset for allergy causative agents that has been published by TRUD, but none of the GP systems currently use it.


## Possible Causes
It will be not be possible for consuming systems to safely trigger comprehensively decision support systems from the allergy codes that GP suppliers currently use, and it applies to secondary care to primary care. 
<br>
This could result in a patient being prescribed/administered incorrect medication which could cause deleterious effects, trigger an allergy or worsen a clinical condition.

## Existing Controls
Consuming systems not being able to understand multiple coding systems some of which are proprietary.
<br>
To note that there is national work to ensure that this situation is resolved and that Gap providers can implement a set of allergy codes that are commonly understood. This hazard will be revisited.

## Design
GP Connect Specification to include the complete record of patient allergies and adverse reactions, including allergies to drugs, foods and substances, and drug interactions.
Specification clearly states the limitation that allergy codes can not be used for decisions support until this is resolved.
<br>
Work is on going to write implementation guidance for GP suppliers.

## Test
n/a 

## Training
n/a

## Business Process Change
The receiving system clinicians will review all allergy headings content (Professional requirement) and then enter appropriate allergy information manually. In GP2GP prescribing module is inactivated until inbound allergy content has been reviewed by the clinician. We recommend alignment to same principle as GP2GP in CareConnect FHIR implementations.
