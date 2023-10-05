## {{page-title}}

This section describes the design approach for Genetic testing information exchange.

## Introduction
Genetic testing is used to support many aspects of patient care, including screening, diagnostic testing, treatment advice and the monitoring and management of rare conditions.

The following describes a simplified, generic genetic test request and test report cycle (without any exception or alternative process flows):

- The Requesting Health Care Professional (HCP) determines that a patient requires a genetic test, for example to aid the diagnosis of a suspected condition or to monitor an existing condition.
- The Requesting HCP sends a test request to a designated genetic laboratory hub in this Home GLH.
- The patient provides a specimen.
- The specimen is collected and sent to the Home GLH.
- Upon receipt at the Home GLH, the specimen is checked and matched with the test request. The details are recorded in the LIMS.
- The specimen is prepared, and the test(s) performed.
- The test report is generated and authorised for release.
- The test report is sent to the Requesting HCP.
- The test report is received by the Requesting HCP. -The patient is informed of the test results and, if required, the Requesting HCP takes further action, for example, initiates a course of treatment, requests further tests or refers the patient to a specialist.

{{render:diagrams-genetic-testing-process-flow}}

There are many possible variations and exceptions to this basic process, including:

- The type of Requesting Organisation (e.g. primary care, secondary care, community) and the role of the Requesting HCP.
- The type of care that the patient is receiving e.g. in-patient, out-patient
- The type and number of required tests.
- Patient consenting for sharing their genomic data for research purposes.
- The type and number of required specimens. Depending on the requested tests, a mix of specimen types may be required e.g. blood and biopsy.
- The organisation and HCP responsible for collecting the specimen and the location, timing and method of collection. In some cases, the Specimen Collecting Organisation and/or HCP may differ from the Requesting Organisation / HCP. For example, in the scenario where a patient is referred by their GP to attend a haematology clinic at a hospital.
- The method used to transport the specimen(s) to the laboratory.
- The processes that are used to handle missing or damaged specimens.
- Whether the Home GLH sends the test request and specimen(s) to another laboratory for analysis. These are known as send-away or referred tests.
- Whether the Home GLH initiates further tests (using the supplied specimens) based on the results of the requested tests. For example, to provide a clearer interpretation of a result or to confirm a diagnosis. These are known as reflex tests.
- Whether one or more interim reports are issued before a final report is sent to the Requesting Organisation.

Several key clinical scenarios are documented in {{pagelink:Home/Design/Clinical-Scenarios}}. These illustrate some of the variations in process outlined above, together with example test reports.

## Technology Scope

As there is a mixed economy in capability of ordering systems and functionality within laboratory information systems, the following technology is in scope for the Alpha:

- Set up of a central service (broker concept): to support messaging capability across organisations enabling electronic test ordering, test status and sample status updates at each organisational boundary. 
- Integrated EPR/LIMS suppliers to enable electronic test ordering, test status and sample tracking via the central broker. 
- The use of a national genomics test requesting portal - to support organisations with low frequency test requesters or a lack of functional capability to integrate their existing systems and may require access to the portal to order genomic tests electronically. 
- Enable GLHs to receive tests requested electronically and receive updates on the test and sample status via the central broker. 
- NGIS integration into core services: enabling the transfer of data captured electronically on WGS Test orders and Record of Discussion with NGIS. 

The long-term aspiration of the programme is to support the use of existing technologies and NHS services wherever possible.  However, there is an understanding that not all Trusts are able to provide this capability and therefore, the use of a central portal in the short term is a viable option.

## A National Test Order Service

{{render:diagrams-central-service}}

Creation of a central test order service, where test requests and related data are stored centrally allows for simple interactions and processes, allows organisations/services to create test requests, notifies organisations of new tasks and is the best option for making test requests and associated information visible to all stakeholders. The solution also makes it
possible to run reporting and monitoring at a national scale for commissioners and support the long term framework for a Unified Genomic Record (UGR).

Integration with a single central service via APIs should be the easiest architecture to interact with for connecting systems, as they only need to integrate API calls into their existing system flows when needed, and only need to do data mapping from their internal data models to those required by the service. There is also only one security model they need to integrate
with.

Currently there are many systems and services connected together either directly or through a regional broker. These current connections could either be used in parallel with a new national service or replaced by the national process where appropriate. A period of rollout and service adoption is expected where there will be a mixed estate of national and regional connections.

## Core Components

### FHIR ServiceRequest & Tasks
The core architecture is based on the FHIR interoperability standard, hence there is the need for the implementation of the services to understand the complexities around the same. 

When a task is passed onto another organisation/service, this indicates a distinct boundary of responsibility. The test ordering service will use FHIR to represent the test request and each task or subtask that is created, as the responsibility crosses these organisation/service boundaries. Each time a task crosses an organisation/service boundary a Task resource will be updated in the test order system representing the work that needs to be fulfilled by the recipient.

{{render:diagrams-genomic-testing-scenario}}

The figure above is an example genomic testing scenario representing the FHIR Service request and related Tasks orchestration. There are a set of common flows between organisations/service which happen currently to fulfil a test request:

- EHR → Sample Management → GLH (Home) → EHR
- EHR → Sample Management → GLH (Home) → GEL → GLH (Home) → EHR
- EHR → Sample Management → GLH (Home) → GLH(Remote) → LGL → GLH (Remote) → GLH (Home) → EHR

For complex test requests such as those for cancer genomic testing, the GLH may send samples to multiple labs, each to run separate tests. The individual labs create interim test reports, which go back to the GLH, where they will be combined to create a final test report for the test request.

There are currently issues around visibility of these tasks sent to the labs, and the interim reports often do not get back to the GLH, causing issues. With the proposed test order system, these problems are addressed by storing a task for each lab, allowing the interim test reports created by each lab to be stored in the test order service, so that the GLH has visibility and can retrieve the reports once submitted.

There may be services which run tests but not initially be connected to the test order service, referred to as black box services. In these scenarios, the GLH should create a task to represent the test being sent to one of these services, but as the service will not be integrated and therefore could not update the task or add a test report, it will be the responsibility of the GLH to update the task and append the test report once they receive it back from the black box test service.

Other models such as the LIMS who would receive the test report in some scenarios could also append it to the test request rather than the GLH, the service should be flexible to meet these use cases, but with the intention that all these edge case services will be connected.

#### National Pathology Exchange (NPEx)
The NPEx is currently connected to most labs, so it is possible that if the national test order service is connected to NPEx many of the updates to tasks, including those for the black box test services, which are not directly connected to the test order service, could be automatically propagated to the service. As most labs participating in the alpha and beta will be connected to the test order service, this will not be considered for inclusion in these stages, though NPEx could be considered as part of a future enhancement to the service.

### FHIR Specimens
As well as tasks being created for each unit of work (e.g. to separate work being conducted across organizational boundaries), it is possible that a new Specimen resources will need to be created as they flow through the system. It is common for a specimen to be processed/changed by a service before it is passed on, this is represented in FHIR through the creation of a sub-specimen of the original (where the original still exists).

In the Test Ordering Service each of these distinct specimens and sub-specimens will be represented by a new FHIR Specimen resource and linked to the task and parent specimen.

The Specimen resource may be created by any organisation, so references from any task might be back to the original specimen if it was just passed directly to the next organisation or a new specimen resource if the organisation processed the specimen before passing it to the next organisation.

**Note:** Specimens created locally and used within the organisation/service, which does not pass outside that organisations/services boundary, will NOT be added to the Test Ordering Service as a new specimen.

