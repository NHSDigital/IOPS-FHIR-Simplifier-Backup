## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> VMP prescription which is fully coded but there is an alternative way of modelling this dosage instruction, see second example below.
</div>

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
      {{xml:example-dosage-sumatriptan}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-2">
      {{json:example-dosage-sumatriptan}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-2">
      {{table:example-dosage-sumatriptan}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-2">
      {{tree:example-dosage-sumatriptan}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Sumatriptan 50mg tablets</div>
1 tablet - take once - as required for Migraine, then 1 tablet - every 2 hours - as required for Migraine - up to a maximum of 6 tablet in 24 hours
</div>

<br/>

### Alternative Representation

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> VMP prescription using a simpler Dosage but where further instructions are text-based.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-3" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-3" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-3" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-3" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-3">
      {{xml:example-dosage-sumatriptan-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-3">
      {{json:example-dosage-sumatriptan-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-3">
      {{table:example-dosage-sumatriptan-alt}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-3">
      {{tree:example-dosage-sumatriptan-alt}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Sumatriptan 50mg tablets</div>
1 tablet - every 2 hours - as required for Migraine - up to a maximum of 6 tablets in 24 hours - Additional doses only to be taken after migraine recurrence
</div>

---