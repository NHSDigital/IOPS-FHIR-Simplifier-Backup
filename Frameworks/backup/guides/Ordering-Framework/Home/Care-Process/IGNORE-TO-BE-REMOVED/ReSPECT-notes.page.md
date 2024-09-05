## {{page-title}}



<table>
<thead>

 <th>Document</th>
 <th>Template</th>
 <th>Resource(s)</th>
</thead>
<tr>
 <td>Is exactly what it says. It is a document often stored in PDF format, but health specific formats exist. 
 
 <br/> 
 
 Examples: Clinic Letter, Discharge Letter, Outpatient Letter, Patient Summary, Observation Chart.

<br/>

NEWS2 Observation Chart 



Bed Charts and Notes



Paper based ReSPECT form

{{render:diagrams-EHR-Record-Types-RespectForm}}

 </td>
 <td>Forms are often used for data entry and contain a series of questions and answers. The answers will be a mix coded and text entries.



<br/> 

Examples include: <a href="https://www.resus.org.uk/respect/respect-healthcare-professionals">ReSPECT</a> <a href="https://www.england.nhs.uk/ourwork/clinical-policy/sepsis/nationalearlywarningscore/">NEWS2/Vital Signs

NEWS2 Data Capture Screen



</a>

One London Care Plan

{{render:diagrams-EHR-Record-Types-oneLondonCarePlan}}


</td>
 <td>
 Resources are built around the common verbs of healthcare such as 
<ul>
<li>Observation</li>
<li>Medication/Prescription Request</li>
<ul>

<br/>

Apple Health Observations



Vital signs monitoring equipment



 </td>
 
</tr>
</table>

All three types of records can be found within the NHS. They all can be found on a single patient [pathway](https://en.wikipedia.org/wiki/Clinical_pathway).

For example, vital signs observations (**resources**) collected from a patient PHR or bedside vital signs monitoring equipment can be used to auto complete a **template**. A completed **template** may result in vital sign observations being created (**resources**). 
When shared with other providers both of these may result in Observation Chart being created and this is stored as a **document**.





This mix of record types is also present on different stages of Roberts journey. His journey was all about `interoperability` but this is a very generic term and this can lead to considerable confusion. 

From a regional or local perscpective we can break down interoperability into five categories, again all of these apply to Roberts journey. 

- {{pagelink:Home/Background/Health-Record-and-Interoperability-Standards/Systems-and-Electronic-Communication.page.md}} discusses the systems used within a typical NHS Hospital and electronic communication which is used to syncronise health administration between these systems. (HL7 v2)
- {{pagelink:Home/Background/Health-Record-and-Interoperability-Standards/Electronic-Health-Records-and-Sharing.page.md}} discusses the standards for recording health data and standards+systems used to access these records. (HL7 FHIR Profiles (UK Core), DICOM, openEHR and IHE XDS/MHD/QEDM)
- {{pagelink:Home/Background/Health-Record-and-Interoperability-Standards/Workflow--Pathways-and-Journeys.page.md}} discusses standards used to coordinate care between the providers on a patients journey. (IHE and FHIR Workflow)
- {{pagelink:Home/Background/Health-Record-and-Interoperability-Standards/Templates.page.md}} Looks at template/form data entry and possible options for standardisation. (openEHR and FHIR Structured Data Capture)
- {{pagelink:Home/Background/Health-Record-and-Interoperability-Standards/Clinical-Documents-and-Health-Summary-Definitions.page.md}} Looks at structured clinical documents which are typically used to provide patient summaries and summary of care (also known as transfer of care). (PRSB and FHIR Documents)

From a NHS England perspective which tends to focus on standards, we have:

THIS IS A WORK IN PROGRESS AND HAS NOT BEEN AGREED. THIS IS PURPOSELY NOT USING NHS ENGLAND DIGITAL DEFINITIONS OF 
- RECORD
- REQUEST
- EVENT

AND SWAPPING INSTEAD TO NHS ENGLAND CLINICAL AND NHS TERMINOLOGY. 
I.E. MOVING FROM TECHNICAL TO CLINICAL PATHWAYS (AND ENGLISH NHS VIEW ON TECH)

<table>
<thead>
   <th>Interoperability Category</th>
   <th>Standards</th>
  </thead>
  <tr>
    <td>  
EHR Records (<b>template</b> and <b>resource</b>)
    </td>
    <td>  
<a href="https://openehr.org/">openEHR</a>
    </td>
  </tr> 
  <tr>
    <td>  
EHR Records (<b>document</b>) 
    </td>
    <td>  
IHE XDS
    </td>
  </tr> 
   <tr>
    <td>  
Sharing of EHR Records (all)
    </td>
    <td>  
IHE MHD (modern XDS), IHE QEDM, INTEROPen CareConnectAPI and HL7 UK FHIR Access. All of these use data models from <a hfref="http://hl7.org/fhir/R4/index.html">FHIR</a> plus UK definitions (CareConnect and UK Core). This focuses on a vendor neutral approaches to sharing EHR records along a patient pathway.
    </td>
  </tr> 
    <tr>
    <td>  
Care Coordination and Electronic Communication
    </td>
    <td>  
<a href="https://www.ihe.net/">IHE</a> (this uses HL7 FHIR) and several FHIR Implementation Guides also fall into this category. This covers care coordination along a patient pathway.
    </td>
  </tr> 
    <tr>
    <td>  
Pathway and Workflow Definitions
    </td>
    <td>  
<a href="https://www.nice.org.uk/">NICE</a>, NHS England Clinical and several clinical and user groups (e.g. <a href="https://gettingitrightfirsttime.co.uk/medical_specialties/diabetes-workstream/">Diabetes UK and GIRFT Diabetes Workstream</a>). This provides definitions of a clinical pathway.
    </td>
  </tr> 
    <tr>
    <td>  
Dataset definitions 
    </td>
    <td>  
<a href=""></a>
<a href="https://theprsb.org/standards/">PRSB</a>, this is high level series of record and record sharing definition. This also includes definitions of clinical correspondence and clinical summaries.
    </td>
  </tr> 
</table>

In addition we have several organisations looking to bring this all together.

| Organisation | Description |
|--
| [INTEROPen](http://www.interopen.org/) | Leading organisations to support & accelerate the delivery and adoption of Interoperability Standards in health & social care |
| [TechUK](https://www.techuk.org/) | | 
| [Kings Fund](https://www.kingsfund.org.uk/) | Ideas that change health and care | 

<br/>
