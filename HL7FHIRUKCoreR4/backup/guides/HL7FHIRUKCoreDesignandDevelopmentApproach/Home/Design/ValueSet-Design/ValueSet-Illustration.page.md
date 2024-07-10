## {{page-title}}

This section is intended to provide examples that illustrate the different ways in which the Content Logical Definition (i.e. the <compose> element and its children elements) might be constructed, depending on the required code system content of the ValueSet.

- <a href="#uksingle">ValueSet containing content from a single entire UK Core CodeSystem</a>

- <a href="#uk+fhir">ValueSet containing selected content from a single FHIR standard CodeSystem and selected content from a single UK Core CodeSystem</a>

- <a href="#uk+null">ValueSet containing content from a multiple UK Core CodeSystems and selected nullFlavors</a>

- <a href="#uk+fhir+exclude">ValueSet containing selected content from a single UK Core CodeSystem and multiple FHIR standard CodeSystems and also excluding specific concepts</a>

- <a href="#snomedindividual">ValueSet containing selected individual codes from SNOMED CT</a>

- <a href="#snomedref">ValueSet containing a single Reference Set from SNOMED CT</a>

- <a href="#snomedsinglehierarchy">ValueSet containing a single hierarchy from SNOMED CT</a>

- <a href="#snomedmultiplehierarchy">ValueSet containing a multiple hierarchies from SNOMED CT</a>

- <a href="#complexvs">Complex ValueSet (SNOMED CT hierarchies and individual codes, and dm+d concept classes)</a>

<br><br>

<h3 id="uksingle"> ValueSet containing content from a single entire UK Core CodeSystem</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-AddressKeyType}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-AddressKeyType}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-AddressKeyType}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-AddressKeyType}}
</div>
</nocheck>
<br>

<h3 id="uk+fhir"> ValueSet containing selected content from a single FHIR standard CodeSystem and selected content from a single UK Core CodeSystem<h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationRequestCourseOfTherapy}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationRequestCourseOfTherapy}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationRequestCourseOfTherapy}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationRequestCourseOfTherapy}}
</div>
</nocheck>
<br>

<h3 id="uk+null" > ValueSet containing content from a multiple UK Core CodeSystems and selected nullFlavors</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-NHSNumberVerificationStatus}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-NHSNumberVerificationStatus}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-NHSNumberVerificationStatus}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-NHSNumberVerificationStatus}}
</div>
</nocheck>
<br>

<h3 id="uk+fhir+exclude" > ValueSet containing selected content from a single UK Core CodeSystem and multiple FHIR standard CodeSystems and also excluding specific concepts</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-PersonRelationshipType}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-PersonRelationshipType}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-PersonRelationshipType}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-PersonRelationshipType}}
</div>
</nocheck>
<br>

<h3 id="snomedindividual" > ValueSet containing selected individual codes from SNOMED CT</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-CompositionCategory}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-CompositionCategory}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-CompositionCategory}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-CompositionCategory}}
</div>
</nocheck>
<br>

<h3 id="snomedref" > ValueSet containing a single Reference Set from SNOMED CT</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationForm}}
</div>
</nocheck>
<br>

<h3 id="snomedsinglehierarchy" > ValueSet containing a single hierarchy from SNOMED CT</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-BodySite}}
</div>
</nocheck>
<br>

<h3 id="snomedmultiplehierarchy" > ValueSet containing a multiple hierarchies from SNOMED CT</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks  active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-VaccinationProcedure}}
</div>
</nocheck>
<br>

<h3 id="complexvs" > Complex ValueSet (SNOMED CT hierarchies and individual codes, and dm+d concept classes)</h3>
<nocheck>
<div class="tab">
 <button class="tablinks" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks active" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent">
  <h3>HTML View</h3>
{{render:https://fhir.hl7.org.uk/ValueSet/UKCore-AllergyCode}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/ValueSet/UKCore-AllergyCode}}
</div>

<div id="XML View" class="tabcontent" style="display:block">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/ValueSet/UKCore-AllergyCode}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/ValueSet/UKCore-AllergyCode}}
</div>
</nocheck>

---
