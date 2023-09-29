## {{page-title}}

Heparin medication is a good example of a complex infusion. A typical treatment starts with a single **loading dose** based on the patient's body weight, followed by a continuous **maintenance dose**, again based on body weight. The dose, expressed as a number of units per kilogram, would be defined by the Heparin protocol implementation by the Trust.

Two sets of loading dose and maintenance are shown below. The first is where the Trust pharmacy team calculate the actual volume of medication to be infused, based on the units per kilogram calculations.

The second set of examples is where the ward clinicians have performed the calulations and these are recorded on the ePMA system. The FHIR standard allows multiple dosing instructions so the examples include the calculated dose as a volume and as a number of 'units'..

In all cases, the patient's body weight is shared within a referenced `Observation` resource.

### Prescribing Events

#### Prescribing Event - Loading Dose

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-51" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-51" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-51" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-51" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-51">
      {{xml:heparin-infusion-request-loading}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-51">
      {{json:heparin-infusion-request-loading}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-51">
      {{table:heparin-infusion-request-loading}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-51">
      {{tree:heparin-infusion-request-loading}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

#### Prescribing Event - Initial Maintenance Dose

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-52" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-52" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-52" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-52" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-52">
      {{xml:heparin-infusion-request-maintenance}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-52">
      {{json:heparin-infusion-request-maintenance}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-52">
      {{table:heparin-infusion-request-maintenance}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-52">
      {{tree:heparin-infusion-request-maintenance}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Note the unit of measure used in the above example is a UCUM unit of **international unit per kilogram per hour**. This could also be expressed as a **rateRatio**. Consumers systems need to be able to handle either type of dosing rate expression.

```xml
<doseAndRate>
	<rateRatio>
		<numerator>
			<value value="18" />
			<unit value="international unit per kilogram" />
			<system value="http://unitsofmeasure.org" />
			<code value="[iU]/kg" />
		</numerator>
		<denominator>
			<value value="1" />
			<unit value="hour" />
			<system value="http://unitsofmeasure.org" />
			<code value="h" />
		</denominator>
	</rateQuantity>
</doseAndRate>
```

#### Prescribing Event - Loading Dose (Calculated)

```
Calculation:
75 units per kilogram x 50 Kg = 3,750 units
20,000 units in 20 mL
Total volume to infuse = 3.75 mL
```

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-53" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-53" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-53" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-53" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-53">
      {{xml:heparin-infusion-request-loading-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-53">
      {{json:heparin-infusion-request-loading-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-53">
      {{table:heparin-infusion-request-loading-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-53">
      {{tree:heparin-infusion-request-loading-calculateddose}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

#### Prescribing Event - Initial Maintenance Dose (Calculated)

```
Calculation:
18 units per kilogram x 50 Kg = 900 units
20,000 units in 20 mL
Total volume to infuse = 0.9 mL
```

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-54" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-54" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-54" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-54" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-54">
      {{xml:heparin-infusion-request-maintenance-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-54">
      {{json:heparin-infusion-request-maintenance-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-54">
      {{table:heparin-infusion-request-maintenance-calculateddose}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-54">
      {{tree:heparin-infusion-request-maintenance-calculateddose}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Typical treatment using Heparin then involves regular blood tests and the maintenance dose to be adjusted as required. Some Trust protocols may require each adjusted dose to be recorded as a new prescription, authorised by a prescriber. This may or may not result in additional `MedicationRequest` resources being shared with the Trust pharmacy system.

Other Trust protocols may leave this to the ward team to make changes as per the protocol (without a further prescription) and the changes in rate to be noted in the medication record as a `MedicationAdministration` event.

### Administration Events

Where there is a need to share the administration record of this patient's Heparin medication, a series of `MedicationAdministration` resources could be generated from the ePMA patient record.

Here we have an example based on the above, but with a series of adjusted doses.

{{ render: example-heparin-admin-record }}{: .img-responsive }

Three data attributes would differ for each `MedicationAdministration` resource. The `effectiveDateTime` and `rateQuantity`, plus the reference to the `MedicationRequest` within `request`.

| Administration | effectiveDateTime | rateQuantity |
|----|----|----|
|Loading dose|2021-03-25T09:00:00+00:00|3.75 mL|
|Initial maintenance dose|2021-03-25T09:05:00+00:00|0.9 mL/h|
|Adjusted maintenance dose|2021-03-25T15:05:00+00:00|1 mL/h|
|Adjusted maintenance dose|2021-03-25T21:05:00+00:00|0.8 mL/h|
|Administration paused for 1 hour|2021-03-26T16:30:00+00:00|Zero administration|
|Adjusted maintenance dose|2021-03-26T17:30:00+00:00|0.8 mL/h|
<!--
<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> There is a current limitation with the FHIR standard for no clear way to describe a period of no medication administration. For this example, pausing the Heparin infusion for 1 hour at 16:30 on 26 March 2021. See the note within this implementation guide for <a href="KnownDosageStructureLimitations#.Periodsofnomedicineadministration">Known Dosage Structure Limitations | Periods of no medicine administration / cyclical prescribing</a>.
</div>
-->
The complete `MedicationAdministration` resource for the first  maintenance dose would be as follows;

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-55" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-55" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-55" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-55" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-55">
      {{xml:heparin-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-55">
      {{json:heparin-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-55">
      {{table:heparin-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-55">
      {{tree:heparin-infusion-administration}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

The complete `MedicationAdministration` resource for the period of zero administration would be as follows;

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-56" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-56" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-56" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-56" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-56">
      {{xml:heparin-infusion-administration-zero}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-56">
      {{json:heparin-infusion-administration-zero}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-56">
      {{table:heparin-infusion-administration-zero}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-56">
      {{tree:heparin-infusion-administration-zero}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---
