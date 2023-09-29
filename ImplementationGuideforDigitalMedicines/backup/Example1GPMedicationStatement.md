<a name="example1"></a>
## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><strong>Note:</strong> This example below is a draft and requires clinical verification.</div>

Chris currently has three active medications:

1. Paracetamol 500mg tablet - take 2 tablets - four times - daily - oral
2. Codeine 30mg tablet - take 2 tablets - four times - daily - oral
3. Ibuprofen 800mg modified-release tablet - take one - two times - daily - oral 

### Actors

**Provider System** = GP System

**Consumer System** = Any system requiring a view of current medication, including a shared patient record

### Example

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
      {{xml:chris-packet-example-1}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-1">
      {{json:chris-packet-example-1}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-1">
      {{table:chris-packet-example-1}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-1">
      {{tree:chris-packet-example-1}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

---