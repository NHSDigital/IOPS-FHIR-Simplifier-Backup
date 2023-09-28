## {{page-title}}

## Data Content Inconsistency

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
        <td>Very Low</td>
        <td>Significant</td>
        <td class="risk1">1</td>
      </tr>
    </table>
  </div>
</div>



## Hazard Description
Data content variation across home countries for e.g. ethnic categories.

## Potential Clinical Impact
Multiple variations in data content or an inconsistent use of terms may lead to difficulties in the interpretation of the record, may result in delayed or inappropriate care.

## Possible Causes
Data content variance across home countries.

## Existing Controls
1. Clinical and technical assurance / governance arrangements.
2. Collaboration across home countries and other stakeholders such as NHS, clinical communities to draw input into design, development and maintenance of UK FHIR core outputs, whilst accounting for variance as appropriate/required.

## Design
Specification and supplier engagement aims for standardisation as far as possible, but where this is not possible:
- Guidance notes provided as part of the specification, making clear of any supplier differences,
- Requirement for relevant informative message to be supplied.

## Test
Specification must be tested as part of clinical assurance and validation. Solution assurance and FOT testing to be completed.

## Training
Local organisation and end-user training to ensure understanding that the purpose of FHIR mapping is to supplement the information available to support patient direct care, not replace any other information sources.

## Business Process Change
n/a
