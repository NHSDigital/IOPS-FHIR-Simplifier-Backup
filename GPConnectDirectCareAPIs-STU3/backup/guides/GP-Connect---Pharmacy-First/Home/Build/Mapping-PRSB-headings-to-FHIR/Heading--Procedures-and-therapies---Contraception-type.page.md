## {{page-title}} <span class="mro-circle required"></span>

> Record entry relating to the patient's use of contraception.

<br />

Recorded within an `Observation.code` as a codeable concept. The code should be a child taken from the SNOMED concept [13197004 | Uses contraception (finding) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=13197004), along with the effective period (start and end date) if known.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
  <b>Note</b>: The review date does not currently have an element in which it can be recorded within the Observation profile - record within the <code>code.text</code> element instead.
</div>


<br />

**Example**

<button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML</button>
<button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table</button>

<div class="example" class="nhsd-!t-margin-bottom-6">
  <div id="XML View" class="tabcontent nhsd-!t-margin-bottom-6" style="display:block"> 
    {{xml:e2360fe6-c866-47e7-b35b-7e263f8bc50e}}
  </div>
  <div id="Table View" class="tabcontent nhsd-!t-margin-bottom-6">
    {{table:e2360fe6-c866-47e7-b35b-7e263f8bc50e}}
  </div>
</div>