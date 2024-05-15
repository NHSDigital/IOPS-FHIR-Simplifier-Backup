---
topic: Background
---
## Background

### Current High Level Business Process
The following diagram illustrates a simplified, high-level “as-is” business process flow for pathology test requesting and reporting for laboratory-based tests:

{{render:path-diagram-high-level-business-process}}

The process is described in more detail below (each of the numbered steps relates to the corresponding process box in the diagram):

1. A Requesting Health Care Professional (HCP), for example a GP, determines that a patient requires a pathology test.
2. The Requesting HCP sends a test request to a designated pathology laboratory (indicated in the diagram above as the Performing Organisation). In many care settings the request is sent to the laboratory electronically using an order comms system however other methods of communicating the request may be used e.g. paper-based forms, email.
3. The specimen is collected and sent to the laboratory.
4. Upon receipt at the laboratory, the specimen is verified (to check that it is suitable for testing) and matched with the test request. The details are recorded (booked) in the Laboratory Information Management System (LIMS).
5. The specimen is prepared for testing. Depending on the type of test, the specimen may need processing prior to the test being performed, for example to separate serum or plasma from a blood specimen.
6. The requested test is performed.
7. The test report containing the results of the test is created and authorised for release.
8. The test report is sent to the Requesting HCP. In many care settings the report is sent electronically, usually via some form of middleware. For example, for primary care requested tests, middleware is typically used to transform the output from the LIMS system into [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) formatted data. The test report data is then transferred to the Requesting HCP using [MESH](https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh).
9. The test report is received by the Requesting HCP and added (filed) into the patient’s record. In most cases an Electronic Patient Record System (EPRS) will be used, for example a GP practice system.
10. The patient is informed of the test results. If required, the Requesting HCP takes further action e.g. to initiate a course of treatment, request further tests or refer the patient to a specialist.

There are many possible variations and exceptions to this basic process, including:

* The **care settings** in which the tests are requested and reported e.g. primary care, secondary care, community-based.
* The type of **Requesting Organisation** (e.g. GP practice, hospital) and/or **Requesting HCP** (e.g. GP, consultant).
* The **type and number of requested tests** – more than one type of test may need to be requested at the same time. Some tests may be requested as a group of related tests. For example, a Full Blood Count typically contains 12 – 14 individual tests. Test groups are often referred to as batteries, panels or profiles. 
* The **type and number of required specimens** – more than one specimen may be required, potentially of different types e.g. blood and urine. 
* The **Specimen Collecting Organisation** and/or **Specimen Collecting HCP** may differ from the Requesting Organisation and/or Requesting HCP. For example, the specimen may be collected by a phlebotomist at a clinic. In many cases a separate appointment is required to collect the specimen(s). Some tests may require a series of specimens to be collected at defined time intervals. These are known as **dynamic function tests**.
* Depending on the type of test, any **specimen pre-conditions** (e.g. fasting status), the **specimen collection method** and/or **specimen collection body site** may need to be recorded as part of the test request and/or test report.
* The **method of transporting the specimen to the laboratory** – this will vary depending on local arrangements and the location of the Specimen Collecting Organisation (which could be the same as the Requesting Organisation) and the laboratory (i.e. the Performing Organisation). For example, tests requested from GP Practices are usually sent to the laboratory by specialist courier services.
* The **type and structure of the test report** – the content, structure and complexity of test reports varies significantly depending on pathology speciality. For example, clinical biochemistry reports usually contain simple atomic test results and associated reference ranges. The results are often quantitative e.g. `Sodium 142 mmol/L`. Other report types can be much more complex. For example, Microscopy, Culture and Sensitivity reports (a type of microbiology investigation) typically contain a mixture of quantitative, qualitive and semi-quantitative results, some of which are presented as a hierarchy. Other report types, such as those used in cellular pathology, usually contain a combination of narrative content and some atomic results, and may also include images.
* The laboratory may send the test request and specimen(s) to another laboratory for analysis. These are known as **send-away** or **referred tests**. 
* The laboratory may initiate further tests (using the supplied specimens) based on the results of the requested tests. These are known as **reflex tests**.
* While a test report is still in progress, a Requesting HCP may ask for further tests to be performed, in addition to those that were originally requested. These are known as **add-on tests**. 
* The laboratory may issue one or more **interim reports** before sending a final report.

### User Stories, Personas and Journey Maps
A set of detailed **User Stories** has been developed to provide further business context for this implementation guide. These can be found on the [Pathology Standards and Implementation work space](https://nhsengland.kahootz.com/PathologyandDiagnostics/view?objectID=37638416), together with other related artefacts such as **Personas** and **Journey Maps**.

### Current GP Practice Pathology Data Flows
The following diagram illustrates the types of systems and associated data flows that are currently used to support GP practice requested pathology tests:

{{render:path-diagram-primary-care-as-is}}

Each of the numbered steps in the diagram is described below:

1. A Health Care Professional in the GP practice determines that a patient requires a pathology test. This is usually done by selecting the relevant patient in the GP practice EPR system and clicking through to an order comms system web portal. Order comms systems are usually hosted by pathology laboratories.
2. A test request is sent from the order comms system to the relevant LIMS. Test requests are usually sent as supplier specific HL7v2.x formatted messages, with local codes used to identify the requested test(s).
3.	Following completion of the requested test(s), a test report is created and output from the LIMS. In common with test requests, test reports are usually defined as supplier specific HL7v2.x formatted messages, with local test codes. 
4.	Most laboratories use middleware systems to support the flow of test reports to GP practice EPR systems. These systems can form part of another system (such as  an order comms system) or can exist as separate, standalone systems. They perform one or more of the following functions:
    * transform the output from LIMS to [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) formatted messages
    * map local laboratory codes to equivalent [Pathology Bounded Code List](https://isd.digital.nhs.uk/trud3/user/guest/group/0/pack/38) (PBCL) Read codes
    * support the routing of messages, via MESH
5.	Using [MESH](https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh), the test report is sent as a PMIP EDIFACT (NHS003) formatted message to the requesting GP practice EPR system.
6.	The message is parsed by the GP practice system and the test report details are added to the patient’s EPR record. As part of this processing, any PBCL Read codes contained within the test report message are mapped to equivalent SNOMED CT PBCL concepts.