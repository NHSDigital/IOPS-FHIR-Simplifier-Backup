## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Dose-based</strong> VTM prescription with maximum dose.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>IMPORTANT:</strong> This example cannot use the simple <code>medicationCodeableConcept</code> element. The VTM medication needs to be qualified with a <code>form</code>. This example uses a <code>contained</code> resource which would be suitable for a RESTful implementation. When using a FHIR Messaging implementation the instance of the <code>Medication</code> resource as another resource within the Bundle.
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
      {{xml:example-dosage-aspirinsuppository}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-2">
      {{json:example-dosage-aspirinsuppository}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-2">
      {{table:example-dosage-aspirinsuppository}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-2">
      {{tree:example-dosage-aspirinsuppository}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Aspirin</div>
Suppository - 600 milligram - every 4 hours - Rectal - up to a maximum of 3.6 gram in 24 hours
</div>

---