## {{page-title}}

### Clinical Scenario

The patient requires 1 gram of Ceftriaxone to be infused over 30 minutes, once a day, for 5 days, for pneumonia.

### Prescribing Event

This `MedicationRequest` is created by the EPMA system for the prescription/order for Ceftriaxone via an infusion. This resource would be made available to the hospital pharmacy.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-01" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-01" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-01" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-01" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-01">
      {{xml:ceftriaxone-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-01">
      {{json:ceftriaxone-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-01">
      {{table:ceftriaxone-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-01">
      {{tree:ceftriaxone-infusion-request}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Dispensing Event: Prepared by Pharmacy

If the infusion is to be prepared by the hospital pharamcy team.

This `Bundle` is created by the pharmacy system for what has been dispensed. A bundle is used in this example because it contains two resources. A `Medication` resource details the two ingredients that have been used to prepare the infusion. A `MedicationDispense` references the `Medication` and details the dosing instruction for the infusion. This bundle would be made available to the ward EPMA system.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-02" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-02" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-02" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-02" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-02">
      {{xml:ceftriaxone-infusion-dispense-combined}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-02">
      {{json:ceftriaxone-infusion-dispense-combined}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-02">
      {{table:ceftriaxone-infusion-dispense-combined}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-02">
      {{tree:ceftriaxone-infusion-dispense-combined}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Dispensing Event: Prepared by Ward

If the infusion is to be prepared by the hospital ward team.

This `Bundle` is created by the pharmacy system for what has been dispensed. A bundle is used in this example because it contains two `MedicationDispense` resources. The first is for the Ceftriaxone powder. The second is for the Sodium chloride diluent. This bundle would be made available to the ward EPMA system. The infusion would be prepared on the ward.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-03" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-03" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-03" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-03" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-03">
      {{xml:ceftriaxone-infusion-dispense-separate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-03">
      {{json:ceftriaxone-infusion-dispense-separate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-03">
      {{table:ceftriaxone-infusion-dispense-separate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-03">
      {{tree:ceftriaxone-infusion-dispense-separate}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Dispensing Event: Dispensed by Pharmacy using a pre-prepared product

Pre-prepared and dm+d coded `Ceftriaxone 1g/50ml infusion bags` products are dispensed to the ward.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-04" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-04" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-04" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-04" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-04">
      {{xml:ceftriaxone-infusion-dispense-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-04">
      {{json:ceftriaxone-infusion-dispense-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-04">
      {{table:ceftriaxone-infusion-dispense-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-04">
      {{tree:ceftriaxone-infusion-dispense-amp}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Administration Event: Using infusion prepared by pharmacy or ward

An administration record using an infusion prepared either by the pharmacy or on the ward. There would be five administration records, one for each infusion, on each day.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-05" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-05" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-05" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-05" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-05">
      {{xml:ceftriaxone-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-05">
      {{json:ceftriaxone-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-05">
      {{table:ceftriaxone-infusion-administration}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-05">
      {{tree:ceftriaxone-infusion-administration}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Administration Event: Using a pre-prepared infusion product

An administration record using a pre-prepared and dm+d coded `Ceftriaxone 1g/50ml infusion bags` product. There would be five administration records, one for each infusion, on each day.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-06" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-06" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-06" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-06" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-06">
      {{xml:ceftriaxone-infusion-administration-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-06">
      {{json:ceftriaxone-infusion-administration-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-06">
      {{table:ceftriaxone-infusion-administration-amp}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-06">
      {{tree:ceftriaxone-infusion-administration-amp}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---
