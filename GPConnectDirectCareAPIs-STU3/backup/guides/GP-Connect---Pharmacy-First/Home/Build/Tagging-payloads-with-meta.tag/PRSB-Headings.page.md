## {{page-title}}

The Professional Records Standards Body (PRSB) has created a series of standards that are used throughout the NHS.

Historically, for Digital Medicines and Transfer of Care, these headings have been represented as record artifacts and HTML (unstructured data).

As the NHS moves to healthcare data that is represented fully structured (where possible) - it has become apparent that a new way of identifying the headings is required so that the various components from the PRSB can be represented in the same way on the receiving system.

The {{pagelink:Home/FHIR-Assets/All-assets/Code-systems/Code-system--RecordStandardHeadings}} **SHOULD BE USED** where necessary to indicate which heading the information being relayed within a profile belongs to.

<br />
<br />

For example, if sending a safeguarding flag, then include the following:

```xml
<Flag xmlns="http://hl7.org/fhir">
    <meta>
        <tag>
            <system value="https://fhir.nhs.uk/CodeSystem/RecordStandardHeadings" />
            <code value="safeguarding" />
            <display value="Safeguarding" />
        </tag>
    </meta>
    ...
</Flag>
```

A receiving system could use this information to present the information within the patient record.

<br />

{{render: gp-record-meta-tag-prsb-headings}}