## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
Dawn discussed improving his diet and suggested physical activity as a method of improving his health.​

She also discussed NHS Prevention Programme's William could make use of including ​
​
<ul>
<li>NHS England - Digital Weight Management.​</li>

<li>NHS Diabetes Prevention Programme​</li>
​</ul>

As William does not have diabetes, he was not eligible for the first programme but will do a diabetes risk assessment for the other on the surgery's patient portal.​

</div>

This section is based on [Type 2 Diabetes Risk](https://riskscore.diabetes.org.uk/start) from [Diabetes UK](https://www.diabetes.org.uk/). This is a recommended evaluation procedure from [NHS England Diabetes Prevention Programme](https://www.england.nhs.uk/diabetes/diabetes-prevention/)

A `structured data capture` form based on the existing [Type 2 Diabetes Risk](https://riskscore.diabetes.org.uk/start) application is shown below: 

{{render:diagrams-Form-DiabetesRiskSDC}}


This has a number of entries common with the previous 'vital signs' form, so is a candidate for `structured data capture` automatic population which can use a `Query API` framework. 

So instead of asking William to reenter values such as height, weight and BMI they were automatically brought in from the previous vital signs form.

Once the assessment has been completed a risk score can be calculated. 

{{render:diagrams-Form-DiabetesUKRisk}}

The process we have followed here is shown in the following sequence diagram.

{{render:diagrams-CareProcess-Diabetes-Risk-Assessment}}

The last part of this diagram indicates the assessment is to be reviewed, this is confirm the referral to the Diabetes Prevention Programme referral should proceed.

Taking a step back we can summarise the journey so far as a business process diagram. 

{{render:diagrams-CareProcess-diabetes-prevention}}

In this diagram, each of the lines connecting the different process boxes is what we are referring to as the `workflow` framework. At each process box, patient care data is being recorded into the patients EPR's, this data is NOT being transferred between the boxes. 

### Physical Activity Intervention Option

This diagram also shows that it is possible for a physical activity intervention to be taking place in parallel with the diabetes prevention programme intervention. Their is likely to be cross over between these interventions and we have the potential of at least three providers providing care at the same time.

In the UK these physical activity interventions are known as `social prescribing` for example [Local Government - Harnessing culture and sport to deliver social prescribing and improve health outcomes](https://www.local.gov.uk/publications/harnessing-culture-and-sport-deliver-social-prescribing-and-improve-health-outcomes) 

There is no recommend UK guidance on the technical implementation of Physical Activity interventions. However [US - Physical Activity Implementation Guide](http://build.fhir.org/ig/HL7/physical-activity/scenarios.html) is consistent with this Implementation Guidance with the similar frameworks and interactions being recommended. 

### Frameworks Used

| Framework | Description |
|--
| {{pagelink:Home/Technical-Framework/Workflow}} | Workflow is used to arrange the completion of the Diabetes Risk questionnaire. | 
| {{pagelink:Home/Technical-Framework/Query-API}} | The Query API was used by Structured Data Capture to source pre-existing data to pre-populate the questionnaire. | 
| {{pagelink:Home/Technical-Framework/Structured-Data-Capture}} |Structured Data Capture was used to define the data to be captured during the health check, this included which SNOMED CT concepts to use and also which units. This defintion was also used in conjunction with Query API to pre-populate the form with existing data.<br/>Structured Data Capture was also used to generate Observations (Events) to be recorded in the surgery EPR. | 
