# {{page-title}}

## User Stories

- Ordering a prescription to a one-off nomination
- Enabling tracking via EPS for a prescription request

<hr>

## Ordering a prescription to a one-off nomination

**As a Patient:**

- I want to order a prescription to a different pharmacy than my normal nominated pharmacy and include the new ODS in the original request

**So that:**

- The details of the new pharmacy can be received by the GP System of the patient’s registered GP Practice and be sent there to be dispensed

### Use Case Flows

### Actors

- Patients
- GP Systems

### Frequency of Use

- Infrequently

### Triggers

- Patient requests a reissue of a prescription via NHS App

### Pre-conditions

- Patient has NHS number
- Patient is logged into NHS App
- Patient selects prescription to reorder
- Patient selects a one off pharmacy nomination

### Post-conditions

- Patient requests reorder 
- GP system receives request
- GP system sends the request to the one off pharmacy to be dispensed

### Main Course

1.	Patient logs into NHS App
2.	Patient selects to order a repeat prescription
3.	Patient selects to order to a one off pharmacy
4.	Request is sent to GP system
5.	GP system approves request
6.	Request is sent to one off nomination
7.	End of course

### Alternate Course

- Patient doesn’t select a one off nomination (no ODS code is included)

### Exception

- NHS App doesn’t have access to ODS code directory

<hr>

## Enabling tracking via EPS for a prescription request

**As a Patient:**

- I want to track my prescription reorder request from end to end, to the point it is ready to be dispensed

**So that:**

- The details of the EPS id is returned to the patient to link it to the dispensing progress

### Use Case Flows

### Actors

- Patients
- GP Systems
- EPS

### Frequency of Use

- Infrequently

### Triggers

- GP accepts request and sends to EPS to be fulfilled

### Pre-conditions

- Patient’s pharmacy is EPS enabled
- Patient orders a prescription through the NHS App
- GP system receives the request and accepts it

### Post-conditions

- The prescription request gets sent to EPS to be dispensed
- Patient checks the status after it is sent

### Main Course

1.	Patient logs in to NHS App
2.	Patient chooses a prescription
3.	Patient orders their prescription
4.	GP accepts the request
5.	The request gets sent to EPS
6.	Patient checks status of order and can see status beyond approved

### Alternate Course

- Patients pharmacy is not EPS enabled

### Exception

N/A

<hr>

## FHIR Assets for Sprint 2

<div>
{{render:All-CodeSystems-CodeSystem-England-PFSPrescriptionOrderingParameter}}
</div>
