## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

### Encounter

<h5><ins>status</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>A Consultation is either 'unknown' (draft) or 'finished' (complete). Only consultations of type 'finished' should be included. However, we require Consumers to ensure Consultations with status 'unknown', (if they are received) to be excluded from the user interface.</p>

---

<h5><ins>type</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more than one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>period</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is the date and time the consultation started.

Please note, a Consultation will have a date / time of when it is recorded and a date / time  that it is referring to. For example, if an individual were to visit a patient on Friday and record it on the Monday. The date advised to be displayed is the Friday date (when the Consultation took place) not the Monday date when it was recorded. 

This is the preferred element date. It is also strongly advised to display only the start date. The end (length) is not always accurate.</p>

---

<h5><ins>length</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>The 'length' element is not advised as safe to display, since it is not always accurate. The automated timer starts at the beginning of the Consultation. A clinician may walk away from the screen for x amount of time, giving an inaccurate length of the Consultation. In some cases, this is manually recorded and is not expected to provide significant useful information </p>

---

### List (Common)

<h5><ins>date</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>It is advised using the ‘period’ start element for the date. If supplementary information is needed for the audit date use the ‘date’ element. The ‘date’ element may be useful to state when the date of the Consultation was last modified on the GP clinical system.</p>

---

### List (Consultation), (Topic) and (Heading)

<h5><ins>title</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The ‘title’ is considered a useful element for Consultations, it’s contextualised information that is recorded against history, action or plan. For example, if an individual adds a procedure with no context of whether it's history or a plan, they could have completely different connotations.</p>

---

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>It’s worth noting that the ‘code’ element will allow Consumers to recognise whether the list is representing a header for the whole consultation, a topic of the consultation or a heading for clinical content. The Consumer could use the ‘code’ to identify the purpose and the meaning of each list.</p>

---

<h5><ins>entry</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The order of entries received is what should be maintained in presenting the information. 
This may have some impact on the context of information displayed to the patient / citizen if the order is not maintained. </p>