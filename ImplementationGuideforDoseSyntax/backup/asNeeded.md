## Element: `asNeeded`

Dosing 'asNeeded' and 'asNeededCodeableConcept' instructions.

### Sub-element: `Dosage.asNeeded[x]`

The `asNeeded` structure can be used to define a simple “as required” (or “pro re nata” expressed as “PRN” for those who still prefer to use Latin abbreviations) instructions. 

In this case use the `asNeededBoolean` option. The absence of `asNeededBoolean` is equivalent to where `asNeededBoolean` has a value of `false`.

The `asNeededCodeableConcept` option is used to bound the dosage instruction to a coded term. Any number of coded terms can be used from the SNOMED-CT hierarchy as a descendant of [404684003 Clinical Finding (finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=404684003&edition=uk-edition). An extensive medication-as-needed-reason value-set is defined within FHIR which is a subset of the SNOMED-CT clinical findings hierarchy.

**Example #1: `Dosage.asNeeded`**

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
      {{xml:example-dosage-inter2}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-1">
      {{json:example-dosage-inter2}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-1">
      {{table:example-dosage-inter2}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-1">
      {{tree:example-dosage-inter2}}
    </div>
  </div>
</div>

<small>Zopiclone 3.75mg tablets, 1 tablet, at BEDTIME, PRN, oral</small>
<!--// end of code snippet -->

<br />

**Example #2: `Dosage.asNeededCodeableConcept`**

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
      {{xml:example-dosage-complex14}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-2">
      {{json:example-dosage-complex14}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-2">
      {{table:example-dosage-complex14}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-2">
      {{tree:example-dosage-complex14}}
    </div>
  </div>
</div>
<small>Metoclopramide, orally 10mg to be taken when required for nausea up to three times daily</small>
<!--// end of code snippet -->

---