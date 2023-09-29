## {{page-title}} <span class="mro-circle required"></span>

> The record of the person’s significant medical, surgical and mental health history. Including relevant previous diagnoses, problems and issues, procedures, investigations, specific anaesthesia issues, etc. (will include dental and obstetric history).

This is a required data item in the Community Pharmacy Standard, which means that Pharmacy Suppliers are obliged to provide this information if it is present within their clinical system.


<br />

Recorded as a free-text string within the `ClinicalImpression.summary` element.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
  <b>Note</b>: The PRSB suggest a member from the <a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=1127581000000103">1127581000000103 | Health issues simple reference set (foundation metadata concept)</a> reference set which has over 125,000 members.
  <br />
  <br />
  It is very unlikely that the entire reference set will be searched to store this information coded, and as such, <b>free text is preferred</b> to record the history in this version of the specification.
</div>

<br />

**Example**

<button class="nhsd-a-button active" onclick="openTab(event, 'XML View')">XML</button>
<button class="nhsd-a-button nhsd-a-button--outline" onclick="openTab(event, 'Table View')">Table</button>

<div class="example" class="nhsd-!t-margin-bottom-6">
  <div id="XML View" class="tabcontent nhsd-!t-margin-bottom-6" style="display:block"> 
    {{xml:4ab82e30-64a6-45df-a171-89102ee02e98}}
  </div>
  <div id="Table View" class="tabcontent nhsd-!t-margin-bottom-6">
    {{table:4ab82e30-64a6-45df-a171-89102ee02e98}}
  </div>
</div>

---