## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
  <strong>Product-based</strong> AMP prescription. Route method, dose duration, and dose expressed a rate ratio.
</div>

**Note:** The `rateRatio` could also be modelled using a UCUM unit within a `doseQuantity`.
In this example we are using the slightly more complex `rateRatio` structure.

e.g.

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


<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-31" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-31" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-31" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-31" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-31">
      {{xml:example-dosage-voluven}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-31">
      {{json:example-dosage-voluven}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-31">
      {{table:example-dosage-voluven}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-31">
      {{tree:example-dosage-voluven}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Voluven 10% infusion 500ml Freeflex bags (Fresenius Kabi Ltd)</div>
Infusion over 10 hours - at a rate of 30 millilitre per kilogram - Intravenous
</div>

---
