## {{page-title}}

### [Link to the High Fidelity Wireframe for the Non WGS Rare Disease Test Scenario](https://2mxvfh.axshare.com)

The following scenario covers the eventuality of a patient being marked a deceased while a test is in progress or in the event a deceased patient's sample is being utilised for further testing on a family member. In some instances, requests may be placed on patients who have died (coroner) and a test/ sample may be requested by the coroner.

In each of these scenarios, the requirement is to allow for testing and reporting to continue until a report has been issued on the patient.

### 1. Requester searches for a patient (a dummy patient has been pre-populated as an example)

**Params:**
```
given=Anita
family=Lamberts
birthdate=eq1993-11-14
```

**Response:**

{{pagelink:Patient-AnitaLambertsDeceasedPatient-Example}}

### 2. Requester searches for test directory code

Call to Digital Test Directory (outside of scope for GMS central broker)

### 3. Requester completes test order form and submits request (patient may be alive or deceased and life status is recorded on the test order form)

POST of test order bundle with {{pagelink:ServiceRequest-NonWGSTestOrderForm-DeceasedPatient-Example}}

(Deceased status or date of death marked on Patient resource: {{pagelink:Patient-AnitaLambertsDeceasedPatient-Example}}

Or

### 1. Test request is on family member

Family members indicated through RelatedPerson resources e.g. {{pagelink:RelatedPerson-AnitaLambertsDeceasedPatient-Example}}

Linked from Patient resource {{pagelink:Patient-AnitaLambertsMotherDeceasedPatient-Example}}

### 2. Sample provided by deceased patient

Specimen resource linked to Patient through subject element as usual.