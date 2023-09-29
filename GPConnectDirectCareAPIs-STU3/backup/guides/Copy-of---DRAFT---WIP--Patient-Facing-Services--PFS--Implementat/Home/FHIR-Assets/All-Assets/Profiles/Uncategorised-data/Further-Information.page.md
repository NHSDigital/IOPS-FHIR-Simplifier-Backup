## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - Not every element will have further information. Further information is to simply give additional context and perspective to the element.
</div>

---

### Observation - uncategorised data

<h5><ins>code</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen).   For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit - 

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

<p>The ‘issued’ element states the date the result was published, not the date when it was taken. </p>

---

<h5><ins>value[x]</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>The ‘value[x]’ element has significant information where it is included but it may also be qualified by other elements such as:

- ‘value\[x]’
- ‘referenceRange’
- ‘interpretation’
- ‘comment’

Note - not all of the bullet point elements will have a value. Some may only have a comment / value or a mix of both.</p>

---

<h5><ins>interpretation</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>For added value and context for the end user (patient / citizen), the advised order is as follows:
- ‘value\[x]’
- ‘referenceRange’
- ‘interpretation’
- ‘comment’

Note - not all of the bullet point elements will have a value. Some may only have a comment / value or a mix of both.</p>

---

<h5><ins>comment</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>For added value and context for the end user (patient / citizen), the advised order is as follows:
- ‘value\[x]’
- ‘referenceRange’
- ‘interpretation’
- ‘comment’</p>

---

<h5><ins>referenceRange</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>It is advised to display the ‘referenceRange’ in a way in which it is immediately clear and obvious that the range value is not the patient's test result but merely the range. There is also a risk that if the ‘referenceRange’ data is separated, the meaning and context may be lost.

For added value and context for the end user (patient / citizen), the advised order is as follows:
- ‘value\[x]’
- ‘referenceRange’
- ‘interpretation’
- ‘comment’</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>component</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is useful, however, there are not many use cases that exist other than blood pressure.</p>

---

### Observation - blood pressure

<h5><ins>code</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen). For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit - 

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release

Please ensure you are aware of the design for modelling blood [pressures in the GP Connect payload](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_uncategoriseddata_guidance#representing-blood-pressure-readings-from-gp-systems).</p>

---

<h5><ins>context</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.</p>

---

<h5><ins>issued</ins></h5>

<span class="fas fa-exclamation-circle text-warning fa-lg" title="Use with caution"></span> Use with caution for PFS

<h5><ins>Further information</ins></h5>

<p>The ‘issued’ element states the date the result was published, not the date when it was taken. The 'effectiveDateTime' element is the most clinically relevant date for the patient / citizen for the majority of anticipated use cases. It is advised to display 'issued' as a secondary item to 'effectiveDateTime' and to clearly distinguish this as secondary information.</p>

---

<h5><ins>related</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>Displaying the element alone will have no meaning to the patient. This is not advised and may cause more confusion than benefit to the user. If a clear business case is portrayed, then this can be utilised in conjunction with other information to represent information free from ambiguity or confusion to the patient / citizen.

Note - if you wish to represent diastolic and systolic blood pressure pairings together. For example, in cases where they have not been presented as a triple, the ‘related’ element will enable this functionality, please see ['Representing blood pressure readings from GP systems']( https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_uncategoriseddata_guidance#representing-blood-pressure-readings-from-gp-systems).</p>

---

### Observation - blood pressure (systolic and diastolic)

<h5><ins>component.code</ins></h5>

<span class="fas fa-check-circle text-success fa-lg"></span>

<h5><ins>Further information</ins></h5>

<p>This element is a CodeableConcept. The element may include more than one code for the medication and/or more one text description. Consumers are strongly advised to use the original term text as the primary text displayed to the end user (patient / citizen).   For more information on 'Processing data from a CodeableConcept', specifically section 'Original term text' then please visit - 

https://simplifier.net/guide/uk-core-implementation-guide/Home/Guidance/CodeableConcept-Guidance?version=1.0.0-pre-release

Please ensure you are aware of the design for modelling blood [pressures in the GP Connect payload](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_uncategoriseddata_guidance#representing-blood-pressure-readings-from-gp-systems).

</p>

---

<h5><ins>component.referenceRange</ins></h5>

<span class="fas fa-times-circle text-danger fa-lg"></span> Not advised for PFS

<h5><ins>Further information</ins></h5>

<p>This element is advised as unsafe for the reason that there isn't a universal reference range that applies to all citizens for all ages. Furthermore, reference range data can occasionally be generated automatically by GP clinical system. Both circumstances are cause for concerns, as incorrect conclusions may be drawn from the reference range.</p>