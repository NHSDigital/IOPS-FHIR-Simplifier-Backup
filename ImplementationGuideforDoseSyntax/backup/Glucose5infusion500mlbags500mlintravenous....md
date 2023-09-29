## Glucose 5% infusion 500ml bags, 500ml, intravenous, continuous infusion, over 8 hours

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
  Non dm+d (ingredient) based prescription. Route, method and dose duration.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-24" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-24" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-24" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-24" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-24">
      {{xml:example-dosage-non-dmd}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-24">
      {{json:example-dosage-non-dmd}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-24">
      {{table:example-dosage-non-dmd}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-24">
      {{tree:example-dosage-non-dmd}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
    <id value="6b122dc2-89b2-4f93-9139-3012f6669857" />
    <contained>
        <Medication>
            <id value="med1" />
            <code>
                <text value="Glucose 5% infusion" />
            </code>
            <form>
                <coding>
                    <system value="http://snomed.info/sct" />
                    <code value="14964511000001102" />
                    <display value="Infusion" />
                </coding>
            </form>
            <ingredient>
                <itemCodeableConcept>
                    <coding>
                        <system value="http://snomed.info/sct" />
                        <code value="768547002" />
                        <display value="Anhydrous Glucose" />
                    </coding>
                </itemCodeableConcept>
                <amount>
                    <numerator>
                        <value value="50" />
                        <unit value="gram" />
                        <system value="http://unitsofmeasure.org" />
                        <code value="g" />
                    </numerator>
                    <denominator>
                        <value value="1" />
                        <unit value="liter" />
                        <system value="http://unitsofmeasure.org" />
                        <code value="L" />
                    </denominator>
                </amount>
            </ingredient>
        </Medication>
    </contained>
    <intent value="order" />
    <status value="active" />
    <medicationReference>
        <reference value="#med1" />
    </medicationReference>
    <subject>
        <identifier>
            <system value="https://fhir.nhs.uk/Id/nhs-number" />
            <value value="9999999999" />
        </identifier>
    </subject>
    <dosageInstruction>
        <timing>
            <repeat>
                <duration value="8" />
                <durationUnit value="h" />
            </repeat>
        </timing>
        <method>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="261754007" />
                <display value="Continuous infusion" />
            </coding>
        </method>
        <doseAndRate>
            <rateRatio>
                <numerator>
                    <value value="100" />
                    <unit value="millilitre" />
                    <system value="http://unitsofmeasure.org" />
                    <code value="mL" />
                </numerator>
                <denominator>
                    <value value="1" />
                    <unit value="hour" />
                    <system value="http://unitsofmeasure.org" />
                    <code value="h" />
                </denominator>
            </rateRatio>
        </doseAndRate>
    </dosageInstruction>
</MedicationRequest>
```

---