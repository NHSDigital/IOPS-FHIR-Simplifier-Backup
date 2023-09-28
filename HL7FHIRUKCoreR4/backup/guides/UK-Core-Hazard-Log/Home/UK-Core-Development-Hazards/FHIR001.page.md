## {{page-title}}

## UK Core is not fully aligned to other Data and professional standards

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
          <td>Significant</td>
          <td class="risk2">2</td>
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
        <td>Significant</td>
        <td class="risk2">2</td>
      </tr>
    </table>
  </div>
</div>


## Hazard Description
The UK Core may not be consistent with the latest version of related
standards e.g. Emergency Care Data Set, SNOMED CT subsets / terminology standards, PRSB standards etc.

## Potential Clinical Impact
Health/care records used in different sites across various clinical and social settings would lack interoperability / standardisation in their records. This could lead to inappropriate care or delay in the delivery of care.

## Possible Causes
1. Limited clinical and  technical (human) resource to ensure alignment of UK Core with other standards.
2. Maintenance of versions of standards cause alignment issues, due to different timeframes, dynamic nature of standards.
3. For certain use case FHIR may not provide complete  mappings which may then require use of FHIR modifier extensions and/or use of other standards
4. Lack of conformance criteria to validate alignment of standards.

## Existing Controls
1. Clinical and technical assurance/  governance arrangements. Collaboration across home countries and other stakeholders such as NHS, clinical communities to draw input into design, development and maintenance of UK FHIR core outputs.
2. UK core includes reference sets / ECL statements which can be manually searched.
3. Ensure FHIR is used only for appropriate use cases and collaborate  with standards body to request changes(s) as required for e/g. access to HL7 UK and International for future changes.
4. Tools are available to prove alignment with UK core, and UK core aligns with FHIR standard, manual checks to ensure alignment across standards.

## Design
Maintenance of the professional standards is the responsibility of PRSB.

## Test
n/a

## Training
n/a

## Business Process Change
n/a
