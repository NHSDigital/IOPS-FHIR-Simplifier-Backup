## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

### DiagnosticReport

<h5><ins>basedOn</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen. Even with a clear use case, please check that it will be supported by having data present from GP clinical systems.</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result, therefore it is advised to be used in such circumstances.</p>

---

<h5><ins>category</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘category’ status indicates the area of the laboratory where the report comes from. This may not be very helpful to users but can be particularly useful when displayed in a group. For example, pathology, microbiology groups. However, this is not always clear, lab reports don't always clearly indicate the type of test lab it's come from.</p>

---

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

This isn't a code of a particular test,  the code here is just a fixed value.

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
However, if there is no specimen date, issue date may be used. (Please note, the date that's most relevant will vary according to your presentation for the data.)</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The DiagnosticReport can refer to more than one specimen. Where this is the case, you may choose to utilise the 'specimen' element to group and organise results. If doing so, ensure the association of individual results in test groups where applicable is maintained.</p>

---

<h5><ins>result</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This is directly equivalent to the element ‘related’ from observation test group header. DiagnosticReport ‘result’ points to the headers, individual results or filing comments. Observation test group header ‘related’ points to results or filing comments.</p>


---

<h5><ins>codedDiagnosis</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept, it is advised to use the original term text as your primary clinical term. For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

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

<h5><ins>collection.extension[fastingStatus]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element can be especially useful when interpreting clinical results. For example, blood sugar level results are lower if the patient has been fasting. Gives the citizen / patient understanding and context.</p>

---

<h5><ins>collection.collected</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is advised as the preferential date to be displayed via PFS. (The date and time when the specimen was drawn).</p>

---

<h5><ins>note</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is not advised to show the ‘note’ element in a summary view via of lab results but must be included with the detail of the specimen.</p>

---

### Observation - test group header

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result, therefore it is advised to be used in such circumstances.</p>

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

This represents the date the batch of tests are recorded as completed. In simple use cases for presenting the whole lab report, this date may not be useful to present as other dates may be more informative to the patient / citizen (e.g. collection date). However, there may be other use cases that can be utilised for this data. In the absence of the preferred dates, you may choose to substitute the date.

<b>LAB REPORT ILLUSTRATION CAN BE LINKED HERE</b> - This isn't presented to be prescriptive as to how to display the data, but it is presented to create a narrative of a scenario. Other display options may be added in future to demonstrate other uses of dates.</p>


---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date).</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The 'specimen' element can be used to group results and obtain common data items such as collection date. This is provided the results remain primarily organised within any test groups they are associated to.</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element must be used to identify the test results and any filing comments relating to this batch header.

This is directly equivalent to the element ‘result’. DiagnosticReport ‘result’ points to the headers, individual results or filing comments. Observation ‘related’ for a header points to results or filing comments.</p>

---

### Observation - test result

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is most useful when it’s a preliminary result, therefore it is advised to be used in such circumstances.</p>

---

<h5><ins>category</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘category’ status indicates the area of the laboratory where the report comes from. In the event that ‘category’ is different across the whole report, you may want to use it to group or to section out the report.

We advise only showing category at the highest level. If everything is all from the same category, then this can be shown at the report level.</p>

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
- 'effective\[x]\' via Observation filing comments - filed date (GP review / annotations - the filing is the act of finalising the sample on the patient record)

This represents the date the batch of tests are recorded as completed. In simple use cases for presenting the whole lab report, this date may not be useful to present as other dates may be more informative to the patient / citizen (e.g. collection date). However, there may be other use cases that can be utilised for this data. In the absence of the preferred dates, you may choose to substitute the date.

<b>LAB REPORT ILLUSTRATION CAN BE LINKED HERE</b> - This isn't presented to be prescriptive as to how to display the data, but it is presented to create a narrative of a scenario. Other display options may be added in future to demonstrate other uses of dates.</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date).</p>

---

<h5><ins>dataAbsentReason</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The element can be used in scenarios such as lab results being lost – which may return a message stating "sample lost, please return". This can be especially useful to a patient / citizen to prompt them to book into the surgery for another sample to be taken.</p>

---

<h5><ins>specimen</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The 'specimen' element can be used to group results and obtain common data items such as collection date. This is provided the results remain primarily organised within any test groups they are associated to.</p>

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

<p>There is no use case defined for the element 'status'. The expectation is it will only ever be set to unknown.</p>

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
- 'effective\[x]\' via Observation filing comments - filed date (GP review / annotations - the filing is the act of finalising the sample on the patient record)

If presenting either the whole report or a part of the report filed to the record (when it becomes visible to the patient / citizen to view). Then the ‘effective[x]’ date from the filing comment is used, you cannot substitute it for anything else.

Or in the scenario of wanting a filing comment on to a lab report but wanted to date the report to the relevant date for the patient. Then the hierarchy displayed above may fit. However, this can all vary depending on other ruse cases.

<b>LAB REPORT ILLUSTRATION CAN BE LINKED HERE</b> - This isn't presented to be prescriptive as to how to display the data, but it is presented to create a narrative of a scenario. Other display options may be added in future to demonstrate other uses of dates.</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The date the lab send out the result, this is not to be confused with the collection.collected date (drawn date).</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This references the test result or test group header that the filing comments resource relates to. However, this is not always going to be populated.

Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

### ProcedureRequest 

<h5><ins>status</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The 'status' element is a fixed value and shouldn't be conveying any meaning in terms of its status. It should always be set as done.</p>

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