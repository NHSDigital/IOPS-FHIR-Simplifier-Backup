## Element: `{{page-title}}`

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
        <a href="#xml-01" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-01" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-01" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-01" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-01">
      {{xml:example-dosage-zopiclone}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-01">
      {{json:example-dosage-zopiclone}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-01">
      {{table:example-dosage-zopiclone}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-01">
      {{tree:example-dosage-zopiclone}}
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
        <a href="#xml-02" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      </li>
      <li role="presentation">
        <a href="#json-02" aria-controls="json" role="tab" data-toggle="tab">JSON</a>
      </li>
        <li role="presentation">
        <a href="#table-02" aria-controls="table" role="tab" data-toggle="tab">Table</a>
      </li>
      <li role="presentation">
        <a href="#tree-02" aria-controls="tree" role="tab" data-toggle="tab">Tree</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-02">
      {{xml:example-dosage-metoclopramide}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-02">
      {{json:example-dosage-metoclopramide}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-02">
      {{table:example-dosage-metoclopramide}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-02">
      {{tree:example-dosage-metoclopramide}}
    </div>
  </div>
</div>
<small>Metoclopramide, orally 10mg to be taken when required for nausea up to three times daily</small>
<!--// end of code snippet -->

---