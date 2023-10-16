# {{page-title}}

## User stories

- [Unscheduled Care Query CP-IS](#user-story-unscheduled-care-query-cp-is)
- [Scheduled Care Query CP-IS](#user-story-scheduled-care-query-cp-is)

<h2 id="user-story-unscheduled-care-query-cp-is">Unscheduled Care Query CP-IS</h2>

**As a Clinician:**

- I can query if a child has a Child Protection Plan

**So that:**

- A local authority is notified of an attendance in unscheduled care

### Use Case Flows

### Actors

- Clinician in unscheduled care setting 
- NHS unscheduled care settings being:
    - emergency departments 
    - walk-in centres 
    - out of hours GPs 
    - minor injuries units 
    - paediatric wards 
    - maternity units 
    - ambulance services

### Frequency of Use

- Real-time

### Triggers

- Patient presents at unscheduled care setting 

### Pre-conditions

- Patient has NHS number 

### Post-conditions

- Patient has been searched on CP-IS

### Main Course

1. The Patient attends at unscheduled care  
1. The clinician has a concern and queries CP-IS by NHS number of child or mother (unborn child)
1. The clinician can view: 
    - details of their plan - type, start date and end date 
    - details of the 25 most recent CP-IS information accesses from unscheduled care settings in England 
    - the name of the responsible local authority, together with their office hours phone and emergency duty contact numbers 
1. The CP-IS query is logged and the responsible local authority is notified

### Alternative Course

1. The Patient attends at unscheduled care  
1. The clinician has a concern and queries CP-IS by NHS number of child or mother (unborn child) 
1. The clinician sees that the child has no child protection plans

### Exception

N/A

<hr>

<h2 id="user-story-scheduled-care-query-cp-is">Scheduled Care Query CP-IS</h2>

**As a Clinician:**

- I can query if a child has a Child Protection Plan

**So that:**

- The clinician can see details of the protection plan. As this is a scheduled (known) encounter the responsible local authority for the child does not need to be notified

### Use Case Flows

### Actors

- Clinician
- NHS scheduled care settings being:
    - Primary Care – General Practice In Hours 
    - Mental Health (CAMHS) 
    - Sexual Health: SARCS & Termination of Pregnancy Services 
    - 0-19 Services 
    - Community Paediatrics 
    - Dentistry 

### Frequency of Use

- Real-time

### Triggers

- Patient attends scheduled care appointment

### Pre-conditions

- Patient has NHS number

### Post-conditions

- Patient has been searched on CP-IS

### Main Course

1. The Patient attends at scheduled care  
1. The clinician queries CP-IS by NHS number of child or mother (unborn child)
1. The clinician can view: 
    - details of their plan - type, start date and end date 
    - details of the 25 most recent CP-IS information accesses from unscheduled care settings in England 
    - the name of the responsible local authority, together with their office hours phone and emergency duty contact numbers 
1. The CP-IS query is logged but no notification is sent to the responsible local authority 

### Alternative Course

1. The patient attends at unscheduled care  
1. The clinician has a concern and queries CP-IS by NHS number of child or mother (unborn child)
1. The clinician sees that the child has no child protection plans

### Exception

N/A

## FHIR Assets for Sprint 1

{{render:ValueSet-England-ChildProtectionPlan}}