---
topic: Home-Guide
---
## UK Core Common Questions ##

<p>
<h3>What is the Scope of FHIR UK Core</h3>
The FHIR UK Core aims to provide a set of generalised profiles, that have been clinically and technically assured for specific use cases, but kept viable in terms of being an enabling standard by defining a broad cardinality and minimum viable content in order to fully support a 4 nation approach and maintain compatibility with the base FHIR standard.
<br>
<br>
It is developed with a constant analysis, and close alignment, to past standards such as CareConnect, future standards such as FHIR R5, and international standards such as US Core and IPS.
<br>
<br>
The FHIR UK Core will never contradict the base FHIR standard but will restrict and extend resources, including amending of any ValueSets and CodeSystems, as necessary to bring in line the UK requirements. The content is relevant to the UK as a whole (4 Nations) although some nation specific CodeSystems are included and referenced in ValueSets.
</p>

<p>
<h3>CareConnect / FHIR STU3</h3>
With the release of STU1 Ballot of FHIR UK Core, the agoal is to have all future FHIR API's produced within NHS England be FHIR R4 compatible, and further development of the CareConnect FHIR STU3 standard will be halted. CareConnect API's will continue to run alongside FHIR R4, but future re-development of CareConnect based services may be uplifted to FHIR R4 and be FHIR UK Core conformant.
<br>
<br>
There is no current timescale within which this will happen, and current implementations of CareConnect APIS should continue to be implemented until a notice of termination is received.
</p>

<p>
<h3>HL7 v2 / v3 Mapping</h3>
There is currently no mappings provided by HL7 UK or the UK Core Development Team between past HL7 standards such as v2 and v3, and the FHIR UK Core. 
<br>
<br>
If you have a specific business use case where this mapping is needed, please contact the UK Core Development Team here: <a href="mailto:interoperabilityteam@nhs.net?Subject=UK Core HL7 v2 Mapping">interoperabilityteam@nhs.net</a>
</p>

<p>
<h3>STU2 Ballot</h3>
FHIR UK Core STU2 Ballot is due to start in Q3 2023, with a 6 week window for comments to be provided. The FHIR UK Core STU2 Ballot covers the Profiles, Extensions, ValueSets, and CodeSystems that underwent clinical and technical assurance under sprints 4, 5, and 6, and cover use cases around fundamental resources, booking and referrals, and diagnostics. 
<br>
<br>
The STU2 Ballot IG can be found <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2?version=1.1.3">here</a>.
</p>

<p>
<h3>Clinical and Technical Assurance</h3>
The next Clincial and Technical Assurance is Sprint 7, and this is scheduled to start in September 2023, with a focus on Clincial Observations, such as vital signs and early warning scores.
<br>
<br>
To find out more about the FHIR UK Core Clinical and Technical Assurance process, click <a href="https://simplifier.net/guide/HL7FHIRUKCoreDesignandDevelopmentApproach/Home/AssuranceandEndorsement/Clinical-and-Technical-Assurance.guide.md?version=current">here</a>.
<br>
<br>
To register your interest in joining the Clinical and Technical Assurance process, or to provide the UK Core Development Team with a use case, please email: <a href="mailto:interoperabilityteam@nhs.net?Subject=Clinical and Technical Assurance">interoperabilityteam@nhs.net</a>
</p>

<p>
<h3>Interacting with the UK Core FHIR Technical Implementation Group</h3>
There are multiple ways to interact with the UK Core FHIR Technical Implementation Group.
<br>
<br>
On chat.fhir.org, we have created a new stream "UK Core FHIR Technical Implementation Group", where you can interact with fellow TIG members, as well as the UK Core Development Team. 
<br>
<br>
The minutes, slide decks, and recordings of UK Core FHIR Technical Implementation Group meetings will be stored on Google Drive under separate folders <a href="https://drive.google.com/drive/folders/18ef8hbICKLc-XqdzYYXZzKTPZTh4tRZo?usp=drive_link">here</a>.
<br>
<br>
Issues can be raised directly with UK Core resources on Simplifier, following the guidance here:
<br>
<br>
And for general enquries, you can email the UK Core Development Team here: <a href="mailto:interoperabilityteam@nhs.net?Subject=UK Core FHIR Technical Implementation Group">interoperabilityteam@nhs.net</a>
</p>

<p>
<h3>SNOMED CT</h3>
SNOMED CT is the preferred clinical terminology CodeSystem used in the UK Core, but as per the CodeableConcept guidance in the STU1 Balloted IG, other CodeSystems, such as READ V2 or CTV3 can be sent. The UK Core Development Team work closely with NHS England Terminology Implementation team to determine clinically and technically assured ValueSets, using expression constraint language (ECL), or reference sets.
<br>
<br>
To learn more about SNOMED CT and the NHS England Terminology Implementation team, please email:  <a href="mailto:information.standards@nhs.net">information.standards@nhs.net</a>
</p>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="I1"><i class="fa fa-legal"></i> Licensing and Publisher</h4>
<ul>
<li> 
Copyright &#169; 2021+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by UK Core Development Team and published by HL7 UK.
</ul>
</div> 

{{render:ukcorelogos2023}}

---