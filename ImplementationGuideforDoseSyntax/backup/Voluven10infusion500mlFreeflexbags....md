## Voluven 10% infusion 500ml Freeflex bags (Fresenius Kabi Ltd), infuse intravenously at a rate of 30ml/kg for 10 hours

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
  <strong>Product-based</strong> prescription. Route method, dose duration, and dose expressed a rate ratio.
</div>

**Note** The `rateRatio` could also be modelled using a UCUM unit within a `doseQuantity`.
In this example we are using the slightly more complex `rateRatio` structre.

```xml
<doseAndRate>
  <doseQuantity>
    <value value="30"/>
    <unit value="millilitres per kilogram"/>
    <system value="http://unitsofmeasure.org"/>
    <code value="ml/kg"/>
  </doseQuantity>
</doseAndRate>
```
<br />

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-25" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-25" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-25" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-25" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-25">
      {{xml:example-dosage-complex17}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-25">
      {{json:example-dosage-complex17}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-25">
      {{table:example-dosage-complex17}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-25">
      {{tree:example-dosage-complex17}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---