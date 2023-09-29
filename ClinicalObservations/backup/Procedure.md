## Procedure

The Clinical Observations implementation uses the Procedure resource which is profiled as below.

---

## UKCore-Procedure ##

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
</div>

---

 ## Conformance Rules ##

 
<a href="#P1">Delivery Route Of Oxygen Supplementation Observation Conformance</a><br/>

Conformance rules to be applied to UKCore-Procedure profile to represent a valid instance for the Clinical Observations exchange of information.

<h2 id="P1">Delivery Route Of Oxygen Supplementation Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>371907003 OR 371908008 OR 9999017 OR 9999016</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>Oxygen administration by nasal cannula OR Oxygen administration by mask OR Oxygen administration by headbox OR High flow oxygen therapy</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Delivery Route Of Oxygen Supplementation observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
