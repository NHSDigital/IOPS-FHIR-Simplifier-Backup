## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Dose-based</strong> VTM prescription with a specific form.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>IMPORTANT:</strong> This example cannot use the simple <code>medicationCodeableConcept</code> element. The VTM medication needs to be qualified with a <code>form</code>. This example uses a <code>contained</code> resource which would be suitable for a RESTful implementation. When using a FHIR Messaging implementation the instance of the <code>Medication</code> resource as another resource within the Bundle.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-15" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-15" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-15" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-15" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-15">
      {{xml:example-dosage-morphinemodified}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-15">
      {{json:example-dosage-morphinemodified}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-15">
      {{table:example-dosage-morphinemodified}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-15">
      {{tree:example-dosage-morphinemodified}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Morphine</div>
Modified-release capsule - 20 milligram - every 12 hours - oral
</div>

---