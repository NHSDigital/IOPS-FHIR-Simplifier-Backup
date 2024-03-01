## {{page-title}}

The proposed central architecture supports the traceability required in the modification of tests or the validity of the test itself based on activity timestamps. This may also include the addition of further tests to a request already submitted. The functional requirement is to enable the modification of test requests both in an incomplete test request state and once the test request has been submitted (inclusion of additional tests requests following submission).

## Modification

In the event the receiving lab requires further information, the requirement is to allow for communication between the lab and requester through means of indication where further information is required on the submitted test. The requester SHALL be notified where additional information is required to proceed with the test and the lab when the update has been made. 

The lab may also update the test request (including clinical indication code) based on the decision made by the clinical scientist. The test may be modified or amended in some instances up to the point of a report being issued. Amendments to a test request SHALL be visible to a user accessing the test request. Details of date, and time and user who made the change SHALL be shown on both the original entry and the amendment. 

The business rules for confirming when modification (e.g., requires further information by requester) is applicable on a submitted test and requires confirmation from the GLHs. 
Modifications, cancellation, and mark in error will be tested for all test request types including WGS Test Requests. Any updates required to enable interoperability and workflow improvements to current practices will be made in coordination with GEL and reflected in the NGIS SOPs. 

## Cancellation

All users of an electronic order management system are responsible for maintaining the accuracy of the tests ordered. In the event a test has been cancelled, the requirement is to allow for transparency on  the reason for cancellation (by either requester or lab) and reflect the changes in real time. When a cancellation occurs, the requirement is to record the date of cancellation, the details of the cancellation. Any changes made SHALL be visible to any user accessing the order management system. 

A test may be cancelled based on some of the example scenarios listed below:
- Test no longer required (i.e., patient has changed their decision to proceed with the test)
- Multiple tests requested on the same patient and where only one test is required
- Decision not to progress with a test request 
- Test could not be delivered due to process failures

## Mark-in Error 

A test may be marked in error when:
- Data has been recorded on the wrong patient
- Sample collected has been aligned to the wrong patient
- Patient choice was incorrectly recorded status (WGS Test Requests only)- correction of patient choice status any time after a test request has been submitted by the GLH
- Correction of clinical data: correction of test information submitted including HPO terms, clinical indications. For WGS Test Requests, the current process for marking at test in error will be tested as part of the requirements validation within the Alpha phase. 

The requirement for managing mark-in-error is to provide transparency to all organisations involved in the provision of the test. Organisations SHALL be informed of the test request being marked in error. If the error was not immediately recognised, information will need to remain to provide an audit trail and reasoning. Details such as reason the test was marked in error, by whom, the date the request and any further information associated with the test request SHALL be maintained.  

Policy guidance is required on how the notification and mark -in-error scenarios are managed across organisational boundaries as all of the different organisations will need to be informed of the Mark-in-Error. 

### [Link to the High Fidelity Wireframe for the Non WGS Rare Disease Test Scenario]https://wi9ul1.axshare.com)

The following steps is a walk through of:

### 1. Requester or Lab searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Meir
family=Lieberman
birthdate=eq2005-12-19
```

**Response:**

{{pagelink:Patient-MeirLiebermanPDS-Example}}

### 2. Requester or Lab views request ordered on the patient

Search on /ServiceRequest?subject:identifier=https://fhir.nhs.uk/Id/nhs-number|9449307873

This would return a searchset bundle containing the ServiceRequest: {{pagelink:ServiceRequest-NonWGSTestOrderForm-Cancellation-Example}}

### 3. Requester or Lab is provided with the functionality to cancel test request

This is recorded through marking the ServiceRequest.status as revoked.

POST of {{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-Cancellation-Example}}

### 4. Requester or Lab indicates reason for cancellation

This is recorded through the associated Provenance resource sent alongside the updated ServiceRequest {{pagelink:Provenance-NonWGSTestOrderFormCancellation-Example}}

### 5. Test displayed as cancelled on patient's test request history

GET of /ServiceRequest?subject:identifier=https://fhir.nhs.uk/Id/nhs-number|9449307873
