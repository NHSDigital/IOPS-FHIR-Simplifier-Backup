## VitalSigns-Observation

The Clinical Observations implementation uses the Observation resource which is profiled as
below.

---

## UKCore-VitalSignsObservation

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation, snapshot}}

 </div>

---

 ## Conformance Rules ##

There are different conformance rules for each vital sign observation type.These conformance rules are applied to the vital signs Observation profile to represent a valid instance for the Clinical Observations exchange of information.

Note: N/A in the source data column indicates elements that are required by the FHIR standard which are not part of the buisness data.


<a href="#P3">Oxygen saturation observation conformance</a><br/> 
<a href="#P4">Heart rate observation conformance</a><br/>
<a href="#P5">Respiration rate observation conformance</a><br/>
<a href="#P6">Blood pressure observation conformance</a><br/>
<a href="#P8">Temperature observation conformance</a><br/>
<a href="#P9">Height / Length observation conformance</a><br/>
<a href="#P10">Head Circumference observation conformance</a><br/>
<a href="#P11">Weight observation conformance</a><br/>
<a href="#P12">Body Mass index observation conformance</a><br/>


---


<h2 id="P3">Oxygen saturation observation conformance</h2> 

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal a code from ECL <code><<103228002 &#124;Hemoglobin saturation with oxygen (observable entity)&#124; MINUS (<<927981000000106 &#124;Baseline oxygen saturation at periphery (observable entity)&#124; OR <<852651000000100 &#124;Maximum peripheral oxygen saturation (observable entity)&#124; OR <<852661000000102 &#124;Minimum peripheral oxygen saturation (observable entity)&#124; OR <<852641000000103 &#124;Target peripheral oxygen saturation (observable entity)&#124; OR <<442349007 &#124;Venous oxygen saturation (observable entity)&#124;)</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>2708-6</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the Oxygen saturation observation was made|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |  
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the oxygen saturation|
||1..1|Observation.valueQuantity.unit.value|must contain <code>%</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>percent</code>



---

<h2 id="P4">Heart rate observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<364075005 &#124;Heart rate (observable entity)&#124; MINUS (<<251670001 &#124;Baseline fetal heart rate (observable entity)&#124; OR <<928001000000104 &#124;Baseline heart rate (observable entity)&#124; OR <<852341000000107 &#124;Maximum pulse rate (observable entity)&#124; OR <<852351000000105 &#124;Minimum pulse rate (observable entity)&#124; OR <<428420003 &#124;Target heart rate (observable entity)&#124; OR <<852331000000103 &#124;Target pulse rate (observable entity)&#124;)</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>8867-4</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information|
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the heart rate was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the number of beats|
||1..1|Observation.valueQuantity.unit.value|must contain <code>beats/min</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>/min</code>
 
---

<h2 id="P5">Respiration rate observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<86290005 &#124;Respiratory rate (observable entity)&#124; MINUS <<927961000000102 &#124;Baseline respiratory rate (observable entity)&#124;</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>9279-1</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|		The date and time that the respiratory rate was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the respiratory rate|
||1..1|Observation.valueQuantity.unit.value|must contain <code>breaths/min</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>/min</code>

---

<h2 id="P6">Blood pressure observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code>75367002</code>|
||1..1|Observation.code.coding.display.value|Blood pressure (observable entity)|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>85354-9</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the blood pressure was taken|
|systolic component|2..2|Observation.component.code||
|systolic component|1..1|Observation.component.code.coding.system.value|must equal <code>http://snomed.info/sct</code>| 
|systolic component|1..1|Observation.component.code.coding.code.value|must equal <code><<271649006 &#124;Systolic blood pressure (observable entity)&#124; MINUS (<<716579001&#124;Baseline systolic blood pressure (observable entity)&#124; OR <<814101000000107&#124;Systolic blood pressure centile (observable entity)&#124; OR <<315612005&#124;Target systolic blood pressure (observable entity)&#124;</code>|
|systolic component|1..1|Observation.component.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
|systolic component|1..1|Observation.component.code.coding.system.value|must equal <code>http://loinc.org</code>| 
|systolic component|1..1|Observation.component.code.coding.code.value|must equal <code>8480-6</code>|
|systolic component|1..1|Observation.component.code.coding.display.value|must equal the display value for the LOINC Concept|
|value|1..1|Observation.component.valueQuantity||
||1..1|Observation.component.valueQuantity.value.value|must contain the systolic pressure|
||1..1|Observation.component.valueQuantity.unit.value|must contain <code>millimeter of mercury</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>mm[Hg]</code>
||1..1|Observation.component.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
|diastolic component|2..2|Observation.component.code||
|diastolic component|1..1|Observation.component.code.coding.system.value|must equal <code>http://snomed.info/sct</code>| 
|diastolic component|1..1|Observation.component.code.coding.code.value|must equal <code><<271650006 &#124;Diastolic blood pressure (observable entity)&#124; MINUS (<<716632005 &#124;Baseline diastolic blood pressure (observable entity)&#124; OR <<814081000000101 &#124;Diastolic blood pressure centile (observable entity)&#124; OR <<315613000 &#124;Target diastolic blood pressure (observable entity)&#124;)</code>|
|diastolic component|1..1|Observation.component.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
|diastolic component|1..1|Observation.component.code.coding.system.value|must equal <code>http://loinc.org</code>| 
|diastolic component|1..1|Observation.component.code.coding.code.value|must equal <code>8462-4</code>|
|diastolic component|1..1|Observation.component.code.coding.display.value|must equal the display value for the LOINC Concept|
|value|1..1|Observation.component.valueQuantity||
||1..1|Observation.component.valueQuantity.value.value|must contain the diastolic pressure|
||1..1|Observation.component.valueQuantity.unit.value|must contain <code>millimeter of mercury</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>mm[Hg]</code>
||1..1|Observation.component.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 

---

<h2 id="P8">Temperature observation conformance</h2>


| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<386725007&#124;Body temperature (observable entity)&#124; MINUS (<<248458005&#124;Comparative temperature in limbs (observable entity)&#124; OR <<852591000000107&#124;Maximum body temperature (observable entity)&#124; OR <<852601000000101&#124;Minimum body temperature (observable entity)&#124; OR <<852581000000105&#124;Target body temperature (observable entity)&#124; OR <<364419004&#124;Temperature of cervical spine (observable entity)&#124; OR <<364424001&#124;Temperature of thoracic spine (observable entity)&#124; OR <<364429006&#124;Temperature of lumbar spine (observable entity)&#124; OR <<248835004&#124;Temperature of breast (observable entity)&#124; OR <<250124002&#124;Temperature of joint (observable entity)&#124; OR <<431197002&#124;Temperature of digit (observable entity)&#124; OR <<364518005&#124;Temperature of foot (observable entity)&#124; OR <<363997004&#124;Temperature of pinna (observable entity)&#124; OR <<364537001&#124;Temperature of skin (observable entity)&#124;)
</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>8310-5</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the temperature reading was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information |
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the temperature reading|
||1..1|Observation.valueQuantity.unit.value|must contain <code>degree Celsius</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>Cel</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>
 
---

<h2 id="P9">Height / Length observation conformance</h2>


| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<50373000&#124;Body height measure (observable entity)&#124; MINUS (<<1060601000000109&#124;Body height growth rate (observable entity)&#124; OR <<422769007&#124;Method for measuring height (observable entity)&#124; OR <<925931000000103&#124;Mid-parental height (observable entity)&#124; OR <<925951000000105&#124;Predicted adult height (observable entity)&#124; OR <<248336007&#124;Pubis to ground height (observable entity)&#124; OR <<276350001&#124;Subischial leg length (observable entity)&#124;)
</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>	8302-2</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the Height / Length measurement was taken|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the Height / Length measurement|
||1..1|Observation.valueQuantity.unit.value|must contain <code>centimeter</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>cm</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>

 
---

<h2 id="P10">Head Circumference observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<363811000&#124;Head circumference measure (observable entity)&#124; MINUS <<248397001&#124;Head circumference centile (observable entity)&#124;
</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>	9843-4</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the Head Circumference measurement was taken|
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the Head Circumference measurement|
||1..1|Observation.valueQuantity.unit.value|must contain <code>centimeter</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>cm</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>

---

<h2 id="P11">Weight observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<27113001&#124;Body weight (observable entity)&#124; MINUS (<<301334000&#124;Birth weight centile (observable entity)&#124; OR <<400967004&#124;Baseline weight (observable entity)&#124; OR <<170804003&#124;Ideal body weight (observable entity)&#124; OR <<852321000000100&#124;Maximum weight (observable entity)&#124; OR <<852311000000106&#124;Minimum weight (observable entity)&#124; OR <<248351003&#124;Previous well-weight (observable entity)&#124; OR <<390734006&#124;Target weight (observable entity)&#124; OR <<363809009&#124;Usual body weight (observable entity)&#124;)
</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>	29463-7</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
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

<h2 id="P12">Body Mass Index observation conformance</h2>

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-VitalSignsObservation profile |
|--
|Status|1..1|Observation.status.value|must equal<code>final</code>|
|N/A|0..1|Observation.category|The category holds a categorization from the sending system |
||1..1|Observation.category.coding.system.value|must equal <code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-VitalSigns-Observation</code>|
||1..1|Observation.category.coding.code.value|must equal <code>vital-signs</code>|
||1..1|Observation.category.coding.display.value|must equal <code>Vital Signs</code>|
|Code|2..2|Observation.code|must have these two instances of the code element|
||1..1|Observation.code.coding.system.value|must equal<code>http://snomed.info/sct</code>
||1..1|Observation.code.coding.code.value|must equal <code><<60621009&#124;Body mass index (observable entity)&#124; MINUS (<<846931000000101&#124;Baseline body mass index (observable entity)&#124; OR <<852451000000103&#124;Maximum body mass index (observable entity)&#124; OR <<852461000000100&#124;Minimum body mass index (observable entity)&#124; OR <<838441000000103&#124;Target body mass index (observable entity)&#124; OR <<715456008&#124;Percentage median body mass index for age and sex (observable entity)&#124;)
</code>|
||1..1|Observation.code.coding.display.value|Wording shall contain the “preferred term” associated with the SNOMED concept|
||1..1|Observation.code.coding.system.value|must equal<code>http://loinc.org</code>
||1..1|Observation.code.coding.code.value|must equal <code>	39156-5</code>|
||1..1|Observation.code.coding.display.value|must equal the display value for the LOINC Concept|
|Subject|1..1|Observation.subject.Reference.Patient|		Who and/or what the observation is about.  See {{pagelink:Patient}} profile for further information| 
|DateTime|1..1|Observation.effectiveDateTime|	The date and time that the BMI measurement was taken| 
|PerformerPerson|0..1|Observation.performer.Reference.Practitioner|		Who is responsible for the observation.  See {{pagelink:Practitioner}}  profile for further information| 
|PerformerOrganization|0..1|Observation.performer.Reference.Organization|		Who is responsible for the observation.  See {{pagelink:Organization}} profile for further information | 
|value|1..1|Observation.valueQuantity||
||1..1|Observation.valueQuantity.value.value|must contain the BMI measurement|
||1..1|Observation.valueQuantity.unit.value|must contain <code>	kilogram / (meter ^ 2)</code>
||1..1|Observation.valueQuantity.code.value|must contain <code>kg/m2</code>
||1..1|Observation.valueQuantity.system.value|must contain <code>http://unitsofmeasure.org</code>


