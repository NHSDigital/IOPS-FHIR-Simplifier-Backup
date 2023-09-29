<a name="example6"></a>
## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><strong>Note:</strong> This example below is a draft and requires clinical verification.
</div>

Codeine has been stopped. Pregabalin has been started. The `MedicationStatement` resources here would be included within any **Discharge Summary** sent to the patient's registered GP practice.

### Actors

**Provider System** = Ward EMPA system

**Consumer System** = Any system requiring a view of current medication, including a shared patient record

### Example

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-2x" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-2x" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-2x" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-2x" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-2x">
      {{xml:chris-packet-example-2x}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-2x">
      {{json:chris-packet-example-x2}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-2x">
      {{table:chris-packet-example-2x}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-2x">
      {{tree:chris-packet-example-2x}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---