## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

<h5><ins>extension[allergyEnd]</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>If the element is marked as ‘untrue’, it will likely be marked in error. In any case, this should not to be sent via PFS.</p>

---

<h5><ins>extension[allergyEnd].endDate</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>There is a strong chance of this element being misunderstood by the end user (patient / citizen). This is not the date the patient has stopped being allergic (person ceasing to be allergic) but when it has been marked by clinical staff as ending.
Additionally, the 'extension[allergyEnd].endReason' element must be populated alongside 'extension[allergyEnd].endDate' to give context to the end user, it is unsafe to only apply end date.</p>

---

<h5><ins>extension[allergyEnd].endReason</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>Similar to 'extension[allergyEnd].endDate'. Furthermore, there is a strong chance of this being misunderstood by the end user (patient / citizen). 
The 'extension[allergyEnd].endReason' element must be populated alongside 'extension[allergyEnd].endDate', it is unsafe to only display the end date element.</p>

---

<h5><ins>clinicalStatus</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element is strongly advised to be supported by the 'extension[allergyEnd].endDate' and 'extension[allergyEnd].endReason'. It may also be used as a header. For example, for active allergies (in the allergy active list) and the other with ended allergies.</p>

---
<h5><ins>type</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>The 'type' element classifies whether it’s an allergy or intolerance. There is an absence of a standard or set of rules for intolerance, sensitivity and how a life-threatening allergy is categorised. Whilst we support what GP clinical systems have in the records, categorising the difference between an allergy and an intolerance can be difficult, the majority of the time there is not enough data to understand the difference. Unless Consumers have a clear understanding of the data, a strong use case and address any risk of inconsistencies, then it is sensible to ignore this element for PFS.</p>

---

<h5><ins>category</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>There are four ‘types’ of identified substance associated with allergies or intolerances. They are food, medication, biologic and environment. However, out of the four, only medication and environment are populated by the GP clinical systems.

The category provided is determined by the source system (GP clinical system). GP Connect advises where there is not a clear assertion by the clinician when recording an allergy and associated category. Categories are assigned based on whether the specified allergy will be used in prescribing and checking (medication) or not (environmental), however this recommendation is not monitored or enforced. 

Unless the PFS has a strong use case to define allergies in this way and can convey the meaning clearly and safely to the user (patient / citizen), then it is not recommended to use this element.</p>

---
<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>onset.DateTime</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is advised to represent the most clinically relevant date which is ‘onset[x]’. However, if secondary dates are used such as ‘assertedDate’, then it should be made clear that these are additional dates. They should not be presented in the same priority as the clinically relevant date (‘onset[x]’).</p>

---

<h5><ins>assertedDate</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>It is advised to represent the most clinically relevant date which is ‘onset[x]’. However, if secondary dates are used such as ‘assertedDate’, then it should be made clear that these are additional dates. They should not be presented in the same priority as the clinically relevant date (‘onset[x]’).</p>

---

<h5><ins>lastOccurence</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS use

<h5><ins>Further information</ins></h5>

<p>Not all GP clinical systems support 'lastOccurence'. For some patients this will not be populated. It is advised to be shown only if populated to avoid confusion and potential wasted real estate of the user interface.</p>

---

<h5><ins>reaction</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Reaction may not be supported by all GP clinical systems. It is currently rare that reaction data is populated.</p>