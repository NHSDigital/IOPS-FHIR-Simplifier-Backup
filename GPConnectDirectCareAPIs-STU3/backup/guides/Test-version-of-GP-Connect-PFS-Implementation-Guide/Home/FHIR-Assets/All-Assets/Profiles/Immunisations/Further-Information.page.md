## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

<h5><ins>extension[recordedDate]</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

The element is an audit trail date or equivalent for the record. This is when it is manually entered into the GP clinical system (or first captured), It is not the date of the immunisation. However, there can be instances where the same date is recorded contemporaneously.

This is not considered the most significant date to a patient / citizen. If used, it should be presented in a less prominent way. 

---

<h5><ins>extension[vaccinationProcedure]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is recommended your primary identifier (or the type of vaccine) is the ‘extension[vaccinationProcedure]’. Where there is additional useful information in ‘vaccineCode’, you may want to also present that information.

This element is a CodeableConcept. The element may include more than one code for the medication and/or more than one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>status</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>The element has values consisting of 'Complete' or 'Entered in error'. Our approach with 'Entered in error' is not to be shown via PFS. Therefore, displaying just the ‘Complete’ value (fixed value) will have no meaning or can be misinterpreted by the patient / citizen.</p>

---

<h5><ins>notGiven</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>The immunization clinical area is designed to support three types of records as captured in GP clinical systems:

1.	Immunisation administration
2.	Intended immunisation administration, which did not occur
3.	Supplementary information related to the process of an immunisation (E.g. sending a letter noting a patient that did not attend their immunisation) 

We believe that the majority of the immunisation use cases will be necessary for the first option on the list. You can ensure you only receive that information by setting the optional parameters appropriately. Should you require about option 2, contact the team (<a href="mailto://gpconnect@nhs.net"> GP Connect team inbox</a>). For option 3 refer to {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Uncategorised-data}} for the structure of the data to be received in our recommendations around the appropriate use of the elements. 
</p>

---

<h5><ins>vaccineCode</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>It is recommended your primary identifier (or the type of vaccine) is the ‘extension[vaccinationProcedure]’. Where there is additional useful information in ‘vaccineCode’, you may want to also present that information.

Note – not all GP clinical systems support ‘vaccineCode’. 

This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>encounter</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.

The element may be useful to show when the vaccine had been given. This can be a linked to the encounter it was given. The elements content is not to be displayed alone but to be used as a link.</p>

---

<h5><ins>date</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>If the element 'date' is not populated, it is advised to use 'not known' as the second option. However, this does not apply to every use case, it will depend on the requirement around the use case.

Note – Not all vaccination dates recorded are in the full dd-mm-yyyy format. Vaccination records may be based on patient recollection or historic paper records. In certain cases, only the approximate date will be known or not at all. Therefore, this could be absent, partial or a full date.
Please consider the above before developing a sorting / filtering functionality. It is advised to make this clear as possible to the patient / citizen using the application.
</p>

---


<h5><ins>primarySource</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>Please be cautious as the default for this Boolean element is set to use true where it is not actually clear in the vaccination record (within in the GP clinical system) as to whether it is a primary or secondary source record.
This can be deemed as unreliable. For example, there may be instances where ‘primarySource’ is unknown, whilst a true or false output will still need to be captured.</p>

---

<h5><ins>reportOrigin</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The ‘reportOrigin‘ is for when ‘primarySource’ is set as false. For example, in this case the origin may be set as ‘school nurse’, otherwise the report origin is recognised as the GP practice.

Not many GP clinical systems capture this information. It is likely that if there is a record from a secondary source, it won’t be identified as such and won’t state what the actual origin of the record is.

This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---

<h5><ins>location</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is specifically stating the physical location (building) of where the vaccination took place, not the where on the body has the patient been injected (body site). This may not be considered as useful information within the Immunisation section.</p>

---

<h5><ins>expirationDate</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is advised to highlight that the expiry date is not suggesting the expiry after it has been administered. But simply when the vaccine expires before use.</p>

---

<h5><ins>explanation.reason</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit -

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release</p>

---