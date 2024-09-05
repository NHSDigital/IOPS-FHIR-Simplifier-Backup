## {{page-title}}

 <div markdown="span" class="alert alert-warning" role="information">
<p>Robert's consultant wishes to rule out a Pulmonary Embolism and so Robert has a CT scan.</p>
</div>

EDMS systems (inc IHE XDS) are normally used as a store for unstructured data items. These include:

- Diagnostic Images
- Clinical Correspondence (discharge letters, outpatient letters, referral letters, etc.)
- Patient correspondence (images of health concern, letters, etc)

They are often accessed via 3rd party products (e.g. a GP System can use DocMan to recording and accessing documents) in the patients record n EPR application will access an EDMS to  and they tend to have the following design:

{{render:diagrams-TechnicalFramework-mhd-cross-enterprise-document-sharing}}

This has three parts:

- **Send Document (1 + 2)** is used to store documents in the EDMS (Document Repository and Registry)
- **Query Document (a)** is used to search for patient documents.
- **Retrieve Document (b)** is used to view the document.


The EDMS product is very likely to have an application which talks directly to the repository, it may or may not use these API's. The API's are primarily for 3rd party access and is commonly used by EPR to display and store documents within those applications.

The number of EDMS accross health and social is quite large. Documents still count for a significant part of a patients health record. Within a single NHS Trust with one EDMS you are likely to find several systems generating documents (including the EPR). This can quickly get out of hand without some level of standardisation. 

{{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} describes API options for sharing clinical documents.
