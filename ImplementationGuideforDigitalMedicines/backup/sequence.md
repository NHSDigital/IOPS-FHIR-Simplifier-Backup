## Element: `{{page-title}}`

Multi-sequence dosage instructions.

A multi-sequence would be required where a dosage instruction changes over a given time schedule, where a dosage instruction includes optional follow-up doses or where a concurrent dosage instruction is required for the same medication at a different dose.

Examples below include Prednisolone to treat Bell’s palsy where a dose starts at 60 mg per day for a period of time then reduces by 10 mg per day. This would be described as a sequential dosage instruction. A concurrent dosage example is provided to describe a different dose in the morning to that at midday.

### Sequential Instructions

Where the value of sequence is an incremental integer it defines a sequential instruction.

**Example use of the FHIR R4 Dosage using multiple sequential sequences**

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-1" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-1" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-1" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-1" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-1">
      {{xml:example-dosage-sequential-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-1">
      {{json:example-dosage-sequential-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-1">
      {{table:example-dosage-sequential-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-1">
      {{tree:example-dosage-sequential-sequence}}
    </div>
  </div>
</div>
<!--// end of code snippet -->


### Concurrent Instructions

Where the same integer value of sequence is defines it means a concurrent instruction.

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-2" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-2" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-2" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-2" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-2">
      {{xml:example-dosage-parallel-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-2">
      {{json:example-dosage-parallel-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-2">
      {{table:example-dosage-parallel-sequence}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-2">
      {{tree:example-dosage-parallel-sequence}}
    </div>
  </div>
</div>
<!--// end of code snippet -->