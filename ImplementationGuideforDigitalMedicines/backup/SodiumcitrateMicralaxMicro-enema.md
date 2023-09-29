## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> AMP prescription.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-26" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-26" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-26" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-26" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-26">
      {{xml:example-dosage-micralax}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-26">
      {{json:example-dosage-micralax}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-26">
      {{table:example-dosage-micralax}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-26">
      {{tree:example-dosage-micralax}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Micralax Micro-enema 5ml (RPH Pharmaceuticals AB)</div>
Insert 1 enema - Rectal - take once
</div>

<br/>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Dose-based</strong> VTM prescription where the quantity of 'Sodium citrate' is defined together with the route. Such medication would typically be prescribed by product (VMP or AMP), as per the above example.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>IMPORTANT:</strong> This example cannot use the simple <code>medicationCodeableConcept</code> element. The VTM medication needs to be qualified with a <code>form</code>. This example uses a <code>contained</code> resource which would be suitable for a RESTful implementation. When using a FHIR Messaging implementation the instance of the <code>Medication</code> resource as another resource within the Bundle.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-27" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-27" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-27" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-27" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-27">
      {{xml:example-dosage-sodiumcitrate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-27">
      {{json:example-dosage-sodiumcitrate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-27">
      {{table:example-dosage-sodiumcitrate}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-27">
      {{tree:example-dosage-simple5-vtm}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Sodium citrate</div>
Enema - Insert 450 milligram - Rectal - take once
</div>

---