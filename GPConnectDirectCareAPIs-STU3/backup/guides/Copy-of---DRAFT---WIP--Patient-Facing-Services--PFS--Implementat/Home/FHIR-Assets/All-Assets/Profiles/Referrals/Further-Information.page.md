## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

<h5><ins>basedOn</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.

We do not currently expect this element to be present. Consumers should check the availability of this information if they have a use case to present it.</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p> This element is fixed to ‘unknown’ (only unknown is used). 

There is potential for the language 'unknown' to be misunderstood by patients or citizens. This may cause them to take an inappropriate action as a consequence.</p>

---

<h5><ins>intent</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>There is potential for the language 'order' to be misunderstood by patients or citizens. This may cause them to take an inappropriate action as a consequence.</p>

---

<h5><ins>priority</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This is the priority assigned to the referral by the practice making the referral. It does not represent the priority being given to the referral by the recipient.</p>

---

<h5><ins>serviceRequested</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>We do not currently expect this element to be present. Consumers should check the availability of this information if they have a use case to present it.

The main coded representation for the referral can be found in ‘reasonCode’. This may be populated if they are supplementary information.

This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>context</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>authoredOn</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is the preferred date for Referrals.</p>

---

<h5><ins>specialty</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>We do not currently expect this element to be present. Consumers should check the availability of this information if they have a use case to present it.

The main coded representation for the referral can be found in ‘reasonCode’. This may be populated if they are supplementary information.</p>

---

<h5><ins>reasonCode</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This will carry the main clinical code used for a referral (to identify the type of referral being made). It is not strictly a reason and will often be a SNOMED referral code.

This element is also a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>supportingInfo</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element may reference a referral letter (or other referral related documentation). Much of the detail of a referral is in the referral letter and not in the referral meta data which this carries. However, this won’t always be linked up.

Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>