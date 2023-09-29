## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> instruction using an AMP. Uses a <code>doseQuantity</code> expressed as a number of <code>Unit</code>. The SNOMED-CT definition of this product contains an attribute for <code>Has unit of administration (attribute)</code> linked to <code>Unit (qualifier value)</code>. This relationship is not contained within dm+d data therefore the <code>medicationCodeableConcept.coding.system</code> is "http://snomed.info/sct" instead of "https://dmd.nhs.uk".<br/><br/><strong>Note:</strong> This representation using a doseQuantity as a number Units should only be used where the consumer system(s) are known to support it. This is opposed to those systems that expect all units of measure to be based on dm+d data such a GP and community pharmacy systems.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-37a" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-37a" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-37a" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-37a" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-37a">
      {{xml:example-dosage-insulin-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-37a">
      {{json:example-dosage-insulin-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-37a">
      {{table:example-dosage-insulin-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-37a">
      {{tree:example-dosage-insulin-alt}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Insulin lispro Sanofi 100units/ml solution for injection 10ml vials (Sanofi)</div>
Inject 8 Unit - 3 times a day - at a meal - Subcutaneous route
</div>

---
