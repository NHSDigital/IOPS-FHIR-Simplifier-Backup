## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

<h5><ins>extension[actualProblem]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>There could be additional information in the resource referenced by ‘extension[actualProblem]’. For example, if the problem was high blood pressure, this may link to a record which has the original blood pressure reading, which may lead to the problem being identified. (The full information of the originally recorded problem that this header represents, is to also read the content of the referred to actual problem.)
This all depends on the use case. If the Consumer is only listing Problems, they might only want the original term (with some metadata associated). In this case ‘extension[actualProblem]’ may not be necessary. If Problems are wanted to be displayed in detail, its highly likely ‘extension[actualProblem]’ will be applied. 

Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>extension[problemSignificance]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This can be useful in a grouped scenario, separating the major and minor Problems (major first followed by minor). It may also be displayed in a condensed summary view. For example, the element may be clearly visible on the user interface without searching or expanding for further information.</p>

---

<h5><ins>clinicalStatus</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>If Consumers are going to present both active and inactive Problems. Then it is advised to utilise this element. 

To clearly and unambiguously distinguish between the active and the inactive Problems being presented to the patient / citizen. This can be done either by separation into separate tables clearly labelled, or clearly labelling each individual Problems.</p>

---

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>context</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a reference to the encounter where the Problem was initially created. Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>abatement</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>If populated ('abatement' is only relevant to inactive Problems).</p>

---

<h5><ins>assertedDate</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The element states the date it was recorded, not when it occurred / happened. If 'onset' date is missing, then use the 'assertedDate'.

The 'assertedDate' element is the date the symptom became classified as being a problem (when the clinician became aware of the symptom). Whereas the ‘onset’ element states the beginning of the symptom. </p>

---

<h5><ins>asserter</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The elemet is a reference to the profile for the practitioner who recorded the Problem. Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>