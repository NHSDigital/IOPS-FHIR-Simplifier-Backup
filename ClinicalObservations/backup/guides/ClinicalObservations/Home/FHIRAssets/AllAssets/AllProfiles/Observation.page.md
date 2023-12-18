---
parent: 
---
## Observation


The Clinical Observations implementation uses the Observation resource which is profiled as below.

---

## UKCore-Observation ##

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Total News2 Score and Observations.</b>
</br>
{{pagelink:totalnews2scoreandobservationsexample}}
</div>

---

## Conformance Rules ##
There are different conformance rules for each observation type. These conformance rules are applied to the Observation profile to represent a valid instance for the Clinical Observations exchange of information.

Note: N/A in the source data column indicates elements that are required by the FHIR standard which are not part of the buisness data.


<a href="#P1">Baseline NEWS2 Score Observation Conformance</a><br/>
<a href="#P2">Baseline NPEWS1 Score Observation Conformance</a><br/>
<a href="#P3">Baseline Oxygen Saturation Observation Conformance</a><br/>
<a href="#P4">Baseline Systolic Observation Conformance</a><br/>
<a href="#P5">Baseline Diastolic Observation Conformance</a><br/>
<a href="#P6">Target Oxygen Saturation Observation Conformance</a><br/>
<a href="#P7">Consciousness Observation Conformance</a><br/>
<a href="#P8">Score Chart Used Observation Conformance</a><br/>
<a href="#P9">Respiration Rate Score Observation Conformance</a><br/>
<a href="#P10">Respiration Distress Observation Conformance</a><br/>
<a href="#P11">Respiration Distress Score Observation Conformance</a><br/>
<a href="#P12">Oxygen Saturation Score Observation Conformance</a><br/>
<a href="#P13">Air or Oxygen Observation Conformance</a><br/>
<a href="#P14">Air or Oxygen Score Observation Conformance</a><br/>
<a href="#P15">Systolic Score Observation Conformance</a><br/>
<a href="#P16">Pulse Rate Score Observation Conformance</a><br/>
<a href="#P17">Capiliary Refill Time Observation Conformance</a><br/>
<a href="#P18">Capiliary Refill Time Score Observation Conformance</a><br/>
<a href="#P19">Consciousness Score Observation Conformance</a><br/>
<a href="#P20">Temperature Score Observation Conformance</a><br/>
<a href="#P21">Patient Concern Observation Conformance</a><br/>
<a href="#P22">Birth Weight Observation Conformance</a><br/>
<a href="#P23">Gestational Age at Birth Observation Conformance</a><br/>
<a href="#P22">NCMP Withdrawal Reason Observation Conformance</a><br/>


---

### Conformance rules to be applied to the UKCore-Observation profile to represent a valid instance for NEWS2 Scores exchange of information. 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
|Early Warning Score type|1..1|||
||1..1|Observation.code.coding.code.value|Must equal the following SNOMED CT concept:<code>"1104051000000101"</code>|
||1..1|Observation.code.coding.display.value|Must equal the stated preferred term for the SNOMED CT concept:<code>"Royal College of Physicians NEWS2 (National Early Warning Score 2) total score"</code>|
||1..1|Observation.code.coding.system.value|Must equal <code>"http://snomed.info/sct"</code>
|Total Score|1..1|Observation.valueQuantity.value|The actual NEWS2 score as a value. Optionally a unit may be sent. If sending a unit then:
||1..1|Observation.valueQuantity.system.value| = <code>http://unitsofmeasure.org</code>| 
||1..1|Observation.valueQuantity.code.value|= <code>&#123;ScoreOf&#125;</code>|
|Total Score Note|0..*|Observation.note.text|Any additional notes or actions that the performer wishes to convey|

---

### Conformance rules to be applied to the UKCore-Observation profile to represent a valid instance for NEWS2  Sub-scores exchange of information. 

Note: the approach is the same, however the sub-score types and values are carried in the observation component element

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
|Early Warning Sub-core type|1..1|||
||1..1|Observation.component.code.coding.code.value|should equal one of the following SNOMED CT concepts|
||1..1|Observation.component.code.coding.display.value|should equal the stated preferred term for the SNOMED CT Concept|
||1..1|Observation.component.code.coding.system.value|Must equal <code>"http://snomed.info/sct"</code>
||||**Concepts and Preferred terms**|
||||<code>1104301000000104 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - respiration rate score</code> |
||||<code>1104311000000102 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - oxygen saturation scale 1 score</code> |
||||<code>1104321000000108 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - oxygen saturation scale 2 score</code> |
||||<code>1104331000000105 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - air or oxygen score</code> |
||||<code>1104351000000103 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - pulse score</code>|
||||<code>1104341000000101 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - systolic blood pressure score</code>
||||<code>1104361000000100 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - consciousness score</code>
||||<code>1104371000000107 - Royal College of Physicians NEWS2 (National Early Warning Score 2) - temperature score</code> |
||||**Note: other types of early warning scores are permissable where supported** |
|Early Warning Sub-score value|1..1|Observation.component.valueQuantity.value|The actual Early Warning Sub-score as a value. Optionally a unit may be sent. If sending a unit then:
||1..1|Observation.component.valueQuantity.system.value| = <code>http://unitsofmeasure.org</code>| 
||1..1|Observation.component.valueQuantity.code.value|= <code>&#123;ScoreOf&#125;</code>|

---

### Conformance rules to be applied to the UKCore-Observation profile to represent a valid instance for NPEWS1 Scores exchange of information. 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
|NPEWS1 Score type|1..1|||
||1..1|Observation.code.coding.code.value|Must equal the following SNOMED CT concept:<code>"1363261000000104"</code>|
||1..1|Observation.code.coding.display.value|Must equal the stated preferred term for the SNOMED CT concept:<code>"NPEWS (National Paediatric Early Warning Score) - total score"</code>|
||1..1|Observation.code.coding.system.value|Must equal <code>"http://snomed.info/sct"</code>
|Total Score|1..1|Observation.valueQuantity.value|The actual NPEWS1 score as a value. Optionally a unit may be sent. If sending a unit then:
||1..1|Observation.valueQuantity.system.value| = <code>http://unitsofmeasure.org</code>| 
||1..1|Observation.valueQuantity.code.value|= <code>&#123;ScoreOf&#125;</code>|
|Total Score Note|0..*|Observation.note.text|Any additional notes or actions that the performer wishes to convey|

---

### Conformance rules to be applied to the UKCore-Observation profile to represent a valid instance for NPEWS1  Sub-scores exchange of information. 

Note: the approach is the same, however the sub-score types and values are carried in the observation component element

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
|NPEWS1 Sub-core type|1..1|||
||1..1|Observation.component.code.coding.code.value|should equal one of the following SNOMED CT concepts|
||1..1|Observation.component.code.coding.display.value|should equal the stated preferred term for the SNOMED CT Concept|
||1..1|Observation.component.code.coding.system.value|Must equal <code>"http://snomed.info/sct"</code>
||||**Concepts and Preferred terms**|
||||<code>1364091000000101 - NPEWS (National Paediatric Early Warning Score) chart used</code> |
||||<code>1363271000000106 - NPEWS (National Paediatric Early Warning Score) - respiration rate score</code> |
||||<code>1364081000000103 - NPEWS (National Paediatric Early Warning Score) - level of respiratory distress</code> |
||||<code>1363301000000109 - NPEWS (National Paediatric Early Warning Score) - respiratory distress score</code> |
||||<code>1363311000000106 - NPEWS (National Paediatric Early Warning Score) - peripheral oxygen saturation score</code>|
||||<code>1363321000000100 - NPEWS (National Paediatric Early Warning Score) - inspired oxygen score</code> |
||||<code>1363291000000105 - NPEWS (National Paediatric Early Warning Score) - systolic blood pressure score</code> |
||||<code>1363331000000103 - NPEWS (National Paediatric Early Warning Score) - heart rate score</code> |
||||<code>1363341000000107 - NPEWS (National Paediatric Early Warning Score) - capillary refill time score</code> |
||||<code>1363351000000105 - NPEWS (National Paediatric Early Warning Score) - consciousness score</code> |
||||<code>1363361000000108 - NPEWS (National Paediatric Early Warning Score) - temperature score</code> |
||||<code>1364131000000103 - NPEWS (National Paediatric Early Warning Score) - nursing concern, clinical intuition</code> |
||||<code>1364121000000100 - NPEWS (National Paediatric Early Warning Score) - how is your child different since I last saw them?</code> |
||||<code>1363261000000104 - NPEWS (National Paediatric Early Warning Score) - total score</code> |
||||**Note: other types of early warning scores are permissable where supported** |
|NPEWS1 Sub-score value|1..1|Observation.component.valueQuantity.value|The actual NPEWS1 Sub-score as a value. Optionally a unit may be sent. If sending a unit then:
||1..1|Observation.component.valueQuantity.system.value| = <code>http://unitsofmeasure.org</code>| 
||1..1|Observation.component.valueQuantity.code.value|= <code>&#123;ScoreOf&#125;</code>|

---

<h2 id="P1">Baseline NEWS2 Score Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>9999100</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>NEWS2 - baseline total score</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Baseline NEWS2 score observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain the baseline NEWS2 score|

---

<h2 id="P2">Baseline NPEWS1 Score Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>1365101000000108</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>NPEWS (National Paediatric Early Warning Score) - baseline total score</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Baseline NPEWS score observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain the baseline NPEWS score|

---

<h2 id="P3">Baseline Oxygen Saturation Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>927981000000106</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>Baseline oxygen saturation at periphery</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Oxygen saturation observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the baseline oxygen saturation|
||1..1|Observation.valueQuantity.unit.value|must contain <code>%</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>percent</code>

---

<h2 id="P4">Baseline Systolic Observation conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>716579001</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>Baseline systolic blood pressure</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Baseline Systolic observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the the baseline Systolic pressure|
||1..1|Observation.valueQuantity.unit.value|must contain <code>	millimeter of mercury</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>mm[Hg]</code>

---

<h2 id="P5">Baseline Diastolic Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>716632005</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>Baseline diastolic blood pressure</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Baseline Diastolic observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the baseline Diastolic pressure|
||1..1|Observation.valueQuantity.unit.value|must contain <code>	millimeter of mercury</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>millimeter of mercury</code>

---

<h2 id="P6">Target Oxygen Saturation Observation Conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>852641000000103</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>Target peripheral oxygen saturation</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Target Oxygen saturation observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the oxygen saturation|
||1..1|Observation.valueQuantity.unit.value|must contain <code>%</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>percent</code>

---

<h2 id="P7">Consciousness Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|Code|1..1|Observation.code||
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal a code from <code>1104441000000107</code>
||1..1|Observation.code.coding.display.value|Must equal <code>Alert Confusion Voice Pain Unresponsive scale score</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Consciousness assessement was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|Value|1..1|Observation.valueCodeableConcept||
||1..1|Observation.valueCodeableConcept.coding.system.value|must equal<code>http://snomed.info/sct</code>|
||1..1|Observation.valueCodeableConcept.coding.code.value|must contain a suitable concept from {{pagelink:VitalSignObservationValue}}
||1..1|Observation.valueCodeableConcept.coding.display.value|must contain the display associated with the concept from {{pagelink:VitalSignObservationValue}}|

---

<h2 id="P8">Score Chart Used Observation Conformance</h2>


| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| Must equal <code>1364091000000101</code>|
||1..1|Observation.code.coding.display.value|	Must equal<code>NPEWS (National Paediatric Early Warning Score) chart used</code>
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Score Chart observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueCodeableConcept.text| must equal one of: <code>0-1 Year,	1-5 year,	5-12 year,	12-16 year</code>|
||1..1|Observation.valueQuantity.value.value|must contain ??|

---

<h2 id="P9">Respiration Rate Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal an ECL code from <code>1104301000000104 OR 1363271000000106</code>|
||1..1|Observation.code.coding.display.value|		must equal <code> Royal College of Physicians NEWS2 (National Early Warning Score 2) - respiration rate score OR NPEWS1 -  NPEWS (National Paediatric Early Warning Score) - respiration rate score|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Respiration Rate observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain the Respiration rate score|

---

<h2 id="P10">Respiration Distress Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1364081000000103</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>NPEWS (National Paediatric Early Warning Score) - level of respiratory distress</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Respiration Distress observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueCodeableConcept.text| must equal one of:  <code> None,	Mild,	Moderate,	Severe</code> |

---

<h2 id="P11">Respiration Distress Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1363301000000109</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>NPEWS (National Paediatric Early Warning Score) - respiratory distress score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Respiration Distress score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain the Respiration Distress score|

---

<h2 id="P12">Oxygen Saturation Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104311000000102 OR 1104321000000108 OR 1363311000000106</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - oxygen saturation scale 1 score OR Royal College of Physicians National Early Warning Score 2 - oxygen saturation scale 2 score OR NPEWS (National Paediatric Early Warning Score) - peripheral oxygen saturation score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Oxygen Saturation Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain the Oxygen Saturation Observation score|

---

<h2 id="P13">Air or Oxygen Observation Conformance</h2>
<h3 id="P13">Air Observation Conformance</h3>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>722742002</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Breathing room air</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Oxygen Saturation Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  

---

<h3 id="P13">Oxygen Observation Conformance</h3>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>371825009  OR 315041000  OR 870533002 </code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Patient on oxygen OR  High concentration oxygen therapy (procedure)  OR  Heated and humidified high flow oxygen therapy</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Oxygen Saturation Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the rate of delivery|
||1..1|Observation.valueQuantity.unit.value|must contain <code>liter per minute</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>L/min</code>

---

<h2 id="P14">Air or Oxygen Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104331000000105 OR 1363321000000100</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - air or oxygen score OR  NPEWS (National Paediatric Early Warning Score) - inspired oxygen score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Air or Oxygen Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Air or Oxygen Observation Score |

---

<h2 id="P15">Systolic Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104341000000101 OR 1363291000000105</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - systolic blood pressure score  OR NPEWS (National Paediatric Early Warning Score) - systolic blood pressure score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Systolic Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Systolic Observation Score |

---

<h2 id="P16">Pulse Rate Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104351000000103 OR 1363331000000103</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - pulse score  OR NPEWS (National Paediatric Early Warning Score) - heart rate score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Pulse Rate Observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Pulse Rate Observation Score |

---

<h2 id="P17">Capiliary Refill Time Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>15527001</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Capillary filling, function</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Capiliary Refill Time Observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the |
||1..1|Observation.valueQuantity.unit.value|must contain <code>s</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>second</code>

---

<h2 id="P18">Capiliary Refill Time Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1363341000000107</code>|
||1..1|Observation.code.coding.display.value|	must equal <code> NPEWS (National Paediatric Early Warning Score) - capillary refill time score</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Capiliary Refill Time score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Capilliary Refill Time Score |

---

<h2 id="P19">Consciousness Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104361000000100 OR 1363351000000105</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - consciousness score  OR NPEWS (National Paediatric Early Warning Score) - consciousness score </code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Consciousness observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Consciousness observation score |

---

<h2 id="P20">Temperature Score Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1104371000000107 OR 1363361000000108</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Royal College of Physicians National Early Warning Score 2 - temperature score  OR NPEWS (National Paediatric Early Warning Score) - temperature score </code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Temperature observation score was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueInteger.value|must contain Temperature observation score |

---

<h2 id="P21">Patient Concern Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code>1364131000000103 or 1364121000000100</code>|
||1..1|Observation.code.coding.display.value|	must equal <code> NPEWS (National Paediatric Early Warning Score) - nursing concern, clinical intuition OR NPEWS (National Paediatric Early Warning Score) - how is your child different since I last saw them? </code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Patient Concern observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueCodeableConcept.text|must equal one of:   <code>Better,	Patient, Asleep, Same, Worse,	Parent Away</code> |

---

<h2 id="P22">Birth Weight Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|Code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code>364589006</code>|
||1..1|Observation.code.coding.display.value|must equal<code>Birth weight</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the Weight measurement was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the Weight measurement|
||1..1|Observation.valueQuantity.unit.value|must contain <code>kg</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>kilogram</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>

---

<h2 id="P23">Gestational Age at Birth Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|Code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code>412726003</code>|
||1..1|Observation.code.coding.display.value|must equal<code> Length of gestation at birth</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the Gestational Age at Birth observation was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the gestational age at birth measurement|
||1..1|Observation.valueQuantity.unit.value|must contain <code>day</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>d</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>

---

<h2 id="P24">NCMP Withdrawal Reason Observation Conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>http://terminology.hl7.org/CodeSystem/observation-category</code>|
||1..1|Observation.category.coding.code.value|must equal <code>survey</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Survey</code>|
|code|1..1|Observation.code|must have one instance of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value| must equal a code from <code><<376251000000101</code>|
||1..1|Observation.code.coding.display.value|	must equal <code>Excluded from national child measurement programme</code>|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the  observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |

