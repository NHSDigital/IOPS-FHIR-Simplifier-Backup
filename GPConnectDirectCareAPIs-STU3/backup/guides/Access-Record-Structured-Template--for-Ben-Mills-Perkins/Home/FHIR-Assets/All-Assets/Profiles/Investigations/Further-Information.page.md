## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

### DiagnosticReport

<h5><ins>basedOn</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result.</p>

---

<h5><ins>category</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘category’ status indicates the area of the laboratory the report goes in to. This may not be very helpful to users but can be particularly useful when displayed in a group. For example, pathology, microbiology groups.</p>

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

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘issued’ element states the date the result was published, not the date when it was taken. 
However, if there is no sample date, issue date may be used.</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element may be used best as a grouper. For example, a blood sample is taken, numerous tests are done from the blood sample. These samples can be useful when grouped to the specimen.</p>

---

<h5><ins>result</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>codedDiagnosis</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>conclusion</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

### Specimen

<h5><ins>type</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>receivedTime</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element may be useful for a clinician to interpret but not for a patient</p>

---

<h5><ins>collection</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element may be useful for a clinician to interpret but not for a patient</p>

---

<h5><ins>collection.extension[fastingStatus]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element can be especially useful when interpreting clinical results. For example, blood sugar level results are lower if the patient has been fasting. Gives the citizen / patient understanding and context.</p>

---

<h5><ins>collection.collected</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as the preferential date to be displayed via PFS. (The date and time when the specimen were drawn).</p>

---

<h5><ins>note</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The 'note' element is advised as a must for PFS.

The element may also be displayed in a detailed (further information) view. For example, if the user patient / citizen wanted to know more, they can expand the user interface for more information. It is not advised to display the element in a condensed quick summary view.</p>

---

### Observation - test group header

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result.</p>

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

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>effective[x]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The aim is to get the closest date to when the sample was taken.

Preferred element order date: 

- 'collection.collected' (The date of the sample (preferred date))
- 'effective\[x]\' (when the batch or tests were conducted)
- 'issued' (result was issued by the laboratory)
- 'effective\[x]\' via Observation filing comments - filed date (GP review / annotations - the filing is the act of finalising the sample on the patient record)</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date.</p>

---

<h5><ins>interpretation</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>comment</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element may be used best as a grouper. For example, a blood sample is taken, numerous tests are done from the blood sample. These samples can be useful when grouped to the specimen.</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

### Observation - test result

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result.</p>

---

<h5><ins>category</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘category’ status indicates the area of the laboratory the report goes in to. This may not be very helpful to users but can be particularly useful when displayed in a group. For example, pathology, microbiology groups.</p>

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

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>effective[x]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The aim is to get the closest date to when the sample was taken.

Preferred element order date: 

- 'collection.collected' (The date of the sample (preferred date))
- 'effective\[x]\' (when the batch or tests were conducted)
- 'issued' (result was issued by the laboratory)
- 'effective\[x]\' via Observation filing comments - filed date (GP review / annotations - the filing is the act of finalising the sample on the patient record)</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date.</p>

---

<h5><ins>value[x]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>dataAbsentReason</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS. The element can be used in scenarios such as lab results being lost result – which may return "sample lost, please return". This can be useful to a patient / citizen to prompt them to get another sample.</p>

---

<h5><ins>interpretation</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>comment</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element may be used best as a grouper. For example, a blood sample is taken, numerous tests are done from the blood sample. These samples can be useful when grouped to the specimen.</p>

---

<h5><ins>referenceRange</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS. Additionally, where the element has multiple values, the reference range will apply to all e.g., blood pressure (systolic and diastolic).</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

### Observation - filing Comments 

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result.</p>

---

<h5><ins>context</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>effective[x]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The aim is to get the closest date to when the sample was taken.

Preferred element order date: 

- 'collection.collected' (The date of the sample (preferred date))
- 'effective\[x]\' (when the batch or tests were conducted)
- 'issued' (result was issued by the laboratory)
- 'effective\[x]\' via Observation filing comments - filed date (GP review / annotations - the filing is the act of finalising the sample on the patient record)</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date.</p>

---

<h5><ins>value[x]</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>comment</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

### ProcedureRequest 

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result.</p>

---

<h5><ins>intent</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>There is potential for the language “order” to be misunderstood by patients or citizens. This may cause them to take an inappropriate action as a consequence.</p>

---

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>reasonReference</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>note</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as a must for PFS.</p>
