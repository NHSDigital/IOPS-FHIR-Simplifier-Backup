## Sending a SNOMED CT concept with its associated preferred term 

When sending a SNOMED CT concept id with its preferred term and the SNOMED CT Description ID is known, then the HL7 common extension `coding-sctdescid` **SHALL** be used and the element `sctdescid` **SHALL** be populated. Where the SNOMED CT Description ID is not known, then the codeable concept **MAY** be sent without it.

In the example below, the SNOMED CT Description ID is populated with the the preferred term, but there is no description ID display as the concept id was entered by the user and the preferred term was displayed to them when it was added.

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
 <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
 <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
 <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{{table:UKCore-Condition-Sn-Extension-CodingSCT-Myocardial-Example}}
</div>

<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{{tree:UKCore-Condition-Sn-Extension-CodingSCT-Myocardial-Example}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:UKCore-Condition-Sn-Extension-CodingSCT-Myocardial-Example}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:UKCore-Condition-Sn-Extension-CodingSCT-Myocardial-Example}}
</div>

---