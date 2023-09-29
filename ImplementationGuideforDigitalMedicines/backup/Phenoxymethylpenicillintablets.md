## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Product-based</strong> VMP prescription using free text additional instruction because 'on an empty stomach' is neither SNOMED coded nor in a FHIR valueset. 
</div>

It was decided that modelling only as 'an hour before food' would not be sufficient. 

```xml
<timing>
    <repeat>
        <when value="C"/>
        <offset value="60" />
    </repeat>
</timing>
```

Therefore a free-text instruction needs to be added.

```xml
<additionalInstruction>
    <text value="or on an empty stomach" />
</additionalInstruction>
```

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#xml-11" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-11" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-11" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-11" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-11">
      {{xml:example-dosage-phenoxymethylpenicillin}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-11">
      {{json:example-dosage-phenoxymethylpenicillin}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-11">
      {{table:example-dosage-phenoxymethylpenicillin}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-11">
      {{tree:example-dosage-phenoxymethylpenicillin}}
    </div>
  </div>
</div>
<!--// end of code snippet -->

Example on-screen presentation:

<div style="background-color:lightgrey;padding:15px;">
<div style="font-size:larger;font-weight:bold;">Phenoxymethylpenicillin 250mg tablets</div>
2 tablet - every 6 hours - 1 hour before a meal - oral - or on an empty stomach
</div>

---