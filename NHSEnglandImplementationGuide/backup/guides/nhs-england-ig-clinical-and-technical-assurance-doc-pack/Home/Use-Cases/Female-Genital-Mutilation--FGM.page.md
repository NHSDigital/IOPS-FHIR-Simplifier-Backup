# {{page-title}}

## User stories

- [View FGM Risk Indicator](#user-story-view-fgm-risk-indicator)
- [Add FGM Risk Indicator](#user-story-add-fgm-risk-indicator)
- [Delete FGM Risk Indicator](#user-story-delete-fgm-risk-indicator)

<h2 id="user-story-view-fgm-risk-indicator">View FGM Risk Indicator</h2>

**As a Healthcare Worker:**

- I can view the patient’s FGM Indicator if the patient has any Family history of FGM

**So that:**

- **TO BE ADDED**

### Use Case Flows

### Actors

- Healthcare worker

### Frequency of Use

- Real-time

### Triggers

- Patient attends health setting and meets criteria for system to trigger FGM status query i.e. under 18 with female genitalia

### Pre-conditions

- Patient has a verified NHS number 

### Post-conditions

- Healthcare worker is made aware of any risk of FGM 

### Main Course

- The patient presents at the care setting
- The healthcare worker is made aware of the patient being at risk of FGM

### Alternative Course

- Patient’s NHS number is not on FGM-IS. Nothing is presented to the health or social care

### Exception

- System exception e.g. network access, RBAC failure, API error

<hr>

<h2 id="user-story-add-fgm-risk-indicator">Add FGM Risk Indicator</h2>

**As a Healthcare Worker:**

- I can add the patient’s FGM risk indicator if the patient has any family history of FGM

**So that:**

- **TO BE ADDED**

### Use Case Flows

### Actors

- Healthcare worker

### Frequency of Use

- Real-time

### Triggers

- Healthcare worker decides that the patient is at risk of FGM. Decision made to add FGM risk indicator. 

### Pre-conditions

- Patient has a verified NHS number 

### Post-conditions

- FGM risk indicator added to FGM-IS for the patient 

### Main Course

- The healthcare worker decides the patient is at risk of FGM
- The healthcare worker adds the risk indicator to FGM-IS

### Alternative Course

- Patient already as an FGM risk indicator on FGM-IS and addition is rejected
- Patient is over 18 and addition of FGM risk indicator is rejected by FGM-IS

### Exception

- System exception e.g. network access, RBAC failure, API error

<hr>

<h2 id="user-story-delete-fgm-risk-indicator">Delete FGM Risk Indicator</h2>

**As a Healthcare Worker:**

- I can delete the patient’s FGM risk indicator if it is no longer required. 

**So that:**

- **TO BE ADDED**

### Use Case Flows

### Actors

- Healthcare worker

### Frequency of Use

- Real-time

### Triggers

- Healthcare worker decides that the patient is no longer at risk of FGM. Decision made to deleted FGM risk indicator

### Pre-conditions

- Patient has a verified NHS number 

### Post-conditions

- FGM risk indicator removed from FGM-IS for the patient

### Main Course

- The healthcare worker decides the patient should not have an FGM risk indicator recorded
- The healthcare worker removes the risk indicator from FGM-IS

### Alternative Course

N/A

### Exception

- System exception e.g. network access, RBAC failure, API error

<hr>

## FHIR Assets for Sprint 1


{{render:Profiles-and-Extensions-All-Extensions-Extension-England-FlagRemovalReason}}

{{render:Home-Terminology-All-CodeSystems-CodeSystem-England-FGMRemovalReason}}

{{render:Guide-Home-Terminology-All-ValueSets-ValueSet-England-FlagRemovalReason}}