## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> instruction using a VMP.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-20" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-20" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-20" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-20" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-20">
      {{xml:example-dosage-gastro}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-20">
      {{json:example-dosage-gastro}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-20">
      {{table:example-dosage-gastro}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-20">
      {{tree:example-dosage-gastro}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Omeprazole 10mg gastro-resistant capsules</div>
1 tablet - daily - oral
</div>

<br/>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Dose-based</strong> instruction using a VTM.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>IMPORTANT:</strong> This example cannot use the simple <code>medicationCodeableConcept</code> element. The VTM medication needs to be qualified with a <code>form</code>. This example uses a <code>contained</code> resource which would be suitable for a RESTful implementation. When using a FHIR Messaging implementation the instance of the <code>Medication</code> resource as another resource within the Bundle.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-21" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-21" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-21" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-21" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-21">
      {{xml:example-dosage-gastro-vtm}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-21">
      {{json:example-dosage-gastro-vtm}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-21">
      {{table:example-dosage-gastro-vtm}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-21">
      {{tree:example-dosage-gastro-vtm}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Omeprazole</div>
gastro-resistant capsule - 10 milligram - daily - oral
</div>

---