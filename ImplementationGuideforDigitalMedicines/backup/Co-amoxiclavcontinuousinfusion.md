## {{page-title}}

To highlight the difference in representing an infusion and an injection using the FHIR standard.

| FHIR Data Item | Infusion | Injection |
|----|----|----|
|`Medication.ingredient` (for the diluent)|Sodium chloride 0.9% infusion 100ml bags|Water for injections 20ml ampoules|
|`dosageInstruction.timing.duration`|over 30 minutes|over 3-4 minutes|
|`dosageInstruction.method`|Continous infusion|Inject|
|`dosageInstruction.doseAndRate`|100 ml|20 ml|

### Prescribing Event - by Infusion

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
      {{xml:co-amoxiclav-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-31">
      {{json:co-amoxiclav-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-31">
      {{table:co-amoxiclav-infusion-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-31">
      {{tree:co-amoxiclav-infusion-request}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

### Prescribing Event - by Injection

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-32" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-32" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-32" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-32" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-32">
      {{xml:co-amoxiclav-injection-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-32">
      {{json:co-amoxiclav-injection-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-32">
      {{table:co-amoxiclav-injection-request}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-32">
      {{tree:co-amoxiclav-injection-request}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---
