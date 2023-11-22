---
topic: BusinessContext
---
### Business Context
The following diagram illustrates a simplified, high-level “as-is” business process flow for pathology test requesting and reporting for laboratory-based tests:

{{render:path-diagram-high-level-business-process}}

{{render:path-diagram-primary-care-as-is}}

{{render:path-diagram-primary-care-to-be}}

The process is described in more detail below (each of the numbered steps relates to the corresponding process box in the diagram):

1.  A Requesting Health Care Professional (HCP), for example a GP, determines that a patient requires a pathology test.
2.  The Requesting HCP sends a test request to a designated pathology laboratory (indicated in the diagram above as the Performing Organisation). In many care settings the request is sent to the laboratory electronically using an order comms system however other methods of communicating the request may be used e.g. paper-based forms, email.
3.  The specimen is collected and sent to the laboratory.
4.  Upon receipt at the laboratory, the specimen is verified (to check that it is suitable for testing) and matched with the test request. The details are recorded (booked) in the Laboratory Information Management System (LIMS).
5.  The specimen is prepared for testing. Depending on the type of test, the specimen may need processing prior to the test being performed, for example to separate serum or plasma from a blood specimen.
6.  The requested test is performed.
7.  The test report containing the results of the test is created and authorised for release.
8.  The test report is sent to the Requesting HCP. In many care settings the report is sent electronically, usually via some form of middleware. For example, for primary care requested tests, middleware is typically used to transform the output from the LIMS system into [PMIP EDIFACT](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) formatted data. The test report data is then transferred to the Requesting HCP using [MESH](https://digital.nhs.uk/services/message-exchange-for-social-care-and-health-mesh).
9.  The test report is received by the Requesting HCP and added (filed) into the patient’s record. In most cases an Electronic Patient Record System (EPRS) will be used, for example a GP practice system.
10. The patient is informed of the test results. If required, the Requesting HCP takes further action e.g. to initiate a course of treatment, request further tests or refer the patient to a specialist.

There are many possible variations and exceptions to this basic process, including:

* The **care settings** in which the tests are requested and reported e.g. primary care, secondary care, community-based.
* The type of **Requesting Organisation** (e.g. GP practice, hospital) and/or **Requesting HCP** (e.g. GP, consultant).
* The **type and number of requested tests** – more than one type of test may need to be requested at the same time. Some tests may be requested as a group of related tests. For example, a Full Blood Count typically contains 12 – 14 individual tests. Test groups are often referred to as batteries, panels or profiles. 
* The **type and number of required specimens** – more than one specimen may be required, potentially of different types e.g. blood and urine. 
* The **Specimen Collecting Organisation** and/or **Specimen Collecting HCP** may differ from the Requesting Organisation and/or Requesting HCP. For example, the specimen may be collected by a phlebotomist at a clinic. In many cases a separate appointment is required to collect the specimen(s). Some tests may require a series of specimens to be collected at defined time intervals. These are known as **dynamic function tests**.
* Depending on the type of test, any **specimen pre-conditions** (e.g. fasting status), the **specimen collection method** and/or **specimen collection body site** may need to be recorded as part of the test request and/or test report.
* The **method of transporting the specimen to the laboratory** – this will vary depending on local arrangements and the location of the Specimen Collecting Organisation (which could be the same as the Requesting Organisation) and the laboratory (i.e. the Performing Organisation). For example, tests requested from GP Practices are usually sent to the laboratory by specialist courier services.
* The **type and structure of the test report** – the content, structure and complexity of test reports varies significantly depending on pathology speciality. For example, clinical biochemistry reports usually contain simple atomic test results and associated reference ranges. The results are often quantitative e.g. <code>Sodium 142 mmol/L</code>. Other report types can be much more complex. For example, Microscopy, Culture and Sensitivity reports (a type of microbiology investigation) typically contain a mixture of quantitative, qualitive and semi-quantitative results, some of which are presented as a hierarchy. Other report types, such as those used in cellular pathology, usually contain a combination of narrative content and some atomic results, and may also include images.
* The laboratory may send the test request and specimen(s) to another laboratory for analysis. These are known as **send-away** or **referred tests**. 
* The laboratory may initiate further tests (using the supplied specimens) based on the results of the requested tests. These are known as **reflex tests**.
* While a test report is still in progress, a Requesting HCP may ask for further tests to be performed, in addition to those that were originally requested. These are known as **add-on tests**. 
* The laboratory may issue one or more **interim reports** before sending a final report.

---
