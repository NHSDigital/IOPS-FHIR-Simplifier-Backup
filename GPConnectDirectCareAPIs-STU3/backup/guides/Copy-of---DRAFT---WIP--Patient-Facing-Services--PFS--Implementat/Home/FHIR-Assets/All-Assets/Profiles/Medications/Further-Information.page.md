## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

### Medication

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more than one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

### MedicationStatement

<h5><ins>extension[lastIssueDate]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is recommended to have the ‘extension[lastIssueDate]’ with 'effective' start date. In some cases, authorization may be made without issue in the medication. In this case, the ‘extension[lastIssueDate]’ will be absent.</p>



---

<h5><ins>extension[prescribingAgency]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>
The element can be split into three codes:

- prescribed-at-gp-practice, with the display of ‘Prescribed at GP Practice’
- prescribed-by-another-organisation, with the display of ‘Prescribed by another organisation’
- prescribed-by-previous-practice, with the display of ‘Prescribed by previous practice’

Depending on the use case, we advise Consumers to consider highlighting those records that are ‘Prescribed by another organisation’ and making it clear that these are not managed by the GP practice. This can be done by either clear indication on the line entry or by separating them into a separate table.
</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The output of 'stopped' from the element 'status' can be used alongside the reason for discontinuation. However, the output of 'completed' or 'active' must not be displayed. On its own this element is not helpful to the end user (patient / citizen), a strong use case is needed for ‘status’ to convey meaning clearly and safely.

For example, the common setting of this element is when GP’s prescribe a course of medication to a patient. At the end of each course, they may then arrange for a blood test. 

The clinical staff issuing the medication will know it is at the end of the course with the element ‘status’ and output of 'complete', then arrange for the patient to come in for a blood test. In this scenario, this element is more beneficial to the clinician issuing the medication than it is for the end user.

A prescription will be ‘complete’ if it has come to the end of an authorisation or review date. If a patient were to see this, they may misinterpret the meaning of the element and stop the medication entirely and not go to a practice to get a reauthorised action as intended.</p>

---

<h5><ins>effective</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is the date range for a period of a prescription (authorisation). This is not the complete date range for an individual taking a given drug.

It is the period believed when the patient will be taking the drug for this authorisation. For a repeat medication this will often have multiple records of authorisations covering different periods (there may be other medication statements or periods before or after for the same drug). Consumers need to be cautious when building this information and how it is conveyed to patients/citizens. In particular, the use of language around dates it presents.
The end date is often a calculated estimation as to when the prescription course will have completed.
</p>

---

<h5><ins>taken</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>This is a mandatory element. GP records cannot consistently say whether the medication has been taken or not. Therefore, is always set to ‘unknown’. It is advised not to show this element as patient/citizen reading that status of ‘unknown may feel the need to contact the GP to update the record to say is has been taken.</p>

---

<h5><ins>note</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>It is advised to display the patient notes. However, this is not to be confused with dispensary notes (pharmacy notes). Only patient notes shall be displayed.
If choosing the ‘note’ element to represent patient notes, the Consumer must strip out the prescriber notes. (Usually located on the left-hand side of a FP10 prescription).</p>

---

<h5><ins>dosage.patientInstruction</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'dosage.patientInstruction' element is additional information for the patient around taking the medication. It is recommended presenting 'dosage.text' then 'dosage.patientInstruction' in the user interface.</p>

---

### MedicationRequest

<h5><ins>extension[repeatInformation]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element will give ability to display "3 issues out of 6 authorisations". This will be especially useful if the patient is coming to the end of a medication. However, the element has different possibilities as to the structure of the information i.e. there may be an authorisation expiry date instead of authorised issue number (or neither).</p>

---

<h5><ins>extension[statusReason].reason</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more than one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>groupIdentifier</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.

For grouping a set of records for an authorization, use the ‘basedOn’ element instead</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.

However, there is an exception for discontinued Medications, 'stopped' can be used but with a reason for discontinuation. Though, 'completed' or 'active' must not be displayed. On its own this element is not helpful to the patient / citizen, grouped with reason this may will help build context.</p>

---

<h5><ins>intent</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>There is potential for the language 'order / plan' to be misunderstood by patients / citizens. This may cause them to take an inappropriate action as a consequence.

This element should be used to differentiate between a medication request that represents the plan / authorization for the medication (covers a similar scope to the associated medication statement) and an individual prescription intent of order. The Consumer must be able to differentiate between these types of medication request record and according to the use case, represent the information appropriately. The element values of order and plan are unlikely to be useful to the user to understand.

Consumers should determine the best way to represent individual prescriptions for medication from an ongoing repeat plan / authorisation.
</p>

---

<h5><ins>medication</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This is a reference to the medication resource. If a Consumer wishes to integrate with other information sources, e.g. link a drugs dictionary with advice pertaining to the individual medication, you may utilise the SNOMED / dm+d coding or description.</p>

---

<h5><ins>context</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised to be used in conjunction with other information rather than it being used on its own. Depending on the use case, it may be worth considering whether there is sufficient value with linking patient medication authorization, for repeat medication to a consultation (which may have additional context). Equally in the case of an order, a linkage could be made. </p>

---

<h5><ins>authoredOn</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>recorder</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>The element is advised as unsafe, it is likely to be interpreted as who prescribed the medication. This can cause more confusion than assistance.</p>

---

<h5><ins>note</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>The 'note' element on MedicationRequest displays the pharmacy notes and is considered not safe or useful for the patient / citizen.</p>

---

<h5><ins>dispenseRequest.validityPeriod</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This is the date prescribers stated the intent for the patient to have a prescription.

Where the intent is plan, the ‘effective’ date can be used from the MedicationStatement. However, in the case of an order, then it is conveying the expected period for that medication to be used at the point it is ordered (it is the intended dispensed date and the intended period during which it would be used).

Furthermore, it is advised to make the date clear / set it in context with other dates (having too many dates displayed at once can overburden, misdirect or lose context for the user). We recommend Consumers implement a clean user interface with meaningful and clear dates for its use cases.

Note – ‘dispenseRequest.validityPeriod’ is not used for the purpose of it being valid for it to be dispensed. It is when the medication is expected to be taken. 

In addition, it is strongly advised to display only the start date. The end (length) is not always precise.
</p>

---

<h5><ins>dispenseRequest.quantity</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is strongly advised to display the quantity alongside the units.</p>

---

<h5><ins>dispenseRequest.performer</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>There is a strong chance this element will not be populated. It is not advised to be displayed.</p>

---

<h5><ins>priorPrescription</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element can reference back to a previous prescription authorisation. The 'priorPrescription' is not to be displayed, only to be used in conjunction with other elements and logical conditions. 

Whilst there may be prior prescriptions, the way they are processed in the in GP clinical systems will not always link the authorisations of prescriptions together. Therefore, this reference will not always be present, even when there is a prior prescription for the same medication or equivalent.
However, if the reference is present, it may be useful information to relay and track through the users (patient / citizen) medication history.

The absence of the link doesn’t always mean there isn’t a story to tell or reference link.
</p>