## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    William Smith is a white middle aged (57) male, who has recently stopped smoking, got married and moved to a new house.​
He has a family history of diabetes and lives in an area with a history of poor health outcomes.​

After speaking the family and friends about his weight, he was recommended to have an NHS Health Check. ​

An NHS Health Check is routinely performed every 5 years from the age of 40. William missed his 55yo checkup as it was during the pandemic, so he decides to ask for one. ​

</div>

This page is based on [NHS Health Check](https://www.nhs.uk/conditions/nhs-health-check/) from NHS England.

William would probably call his surgery to arrange a check up or consultation with his GP. 

The GP probably reviewed Williams record, if external systems were used then this could use a {{pagelink:Home/Technical-Framework/Query-API}}. 
The GP could have taken some observations but we will assume the practice nurse did this. 
The observations Dawn was asked to collect was probably a version of  'vital-signs' and would be captured and recorded into the GP system, probably via a form or template similar to the screen shot below.

{{render:diagrams-Form-VitalSignsSDC}}

In IHE the process of sharing this form with an external system is called [Retrieve Form for Data Capture (RFD)](https://profiles.ihe.net/ITI/TF/Volume1/ch-17.html), the HL7 FHIR 
{{pagelink:Home/Technical-Framework/Structured-Data-Capture}} builds on this and adds:

- *Form Definition* - is used to define what data is to be captured and what codes and units to use
- *Automatic Population* - which reduces the pain of copying data between applications. 
- *Rendering Considerations* - which provides guidance on how the form should be displayed to a user.
- *Data Extraction* - How the form data could be shared with other applications and users.

An example of a form definition can be found here: {{pagelink:Home/Artefacts/Questionnaire/Vital-Signs-Findings.page.md}} 
The output of the completed form in FHIR format is a QuestionnaireResponse {{pagelink:Home/Artefacts/QuestionnaireResponse/Vital-Signs-Completed-Form.page.md}} 
This form can also be **extracted** into other formats such as FHIR Observations, for example a SP02 measurement {{pagelink:Home/Artefacts/Observation/SP02.page.md}}. 

### Frameworks Used

| Framework | Description |
|--
| {{pagelink:Home/Technical-Framework/Workflow}} | Workflow could be used to arrange the Health Check | 
| {{pagelink:Home/Technical-Framework/Query-API}} | The practitioner probably reviewed the patient record record using a native Query API.<br/>The Query API was used by Structured Data Capture to source pre-existing data to pre-populate the questionnaire.|
| {{pagelink:Home/Technical-Framework/Structured-Data-Capture}} | Structured Data Capture was used to define the data to be captured during the health check, this included which SNOMED CT concepts to use and also which units. This defintion was also used in conjunction with Query API to pre-populate the form with existing data.<br/>Structured Data Capture was also used to generate Observations (Events) to be recorded in the surgery EPR.| 
