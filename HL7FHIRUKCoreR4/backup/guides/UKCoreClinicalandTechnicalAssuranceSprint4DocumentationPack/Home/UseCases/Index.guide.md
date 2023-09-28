# Use Cases

For the FHIR UK Core to develop it requires use cases to influence the content of its assets and associated Implementation Guide (IG).  This document has been structured to allow the IOPS team to understand the business use case and how it relates to the FHIR assets, in turn it will help standardise the implementation of FHIR within the UK. 

Any requests for new, or changes to, assets shall have a business use case:

## Business Use Case
A brief summary of why the FHIR asset is needed, i.e., its purpose. It may be worth explaining the problem by:

**As a ***[health care role]*** I want *...* so that *...***

The use case should also include:

**Actors (for sending)**: *Where does the information come from, e.g. a doctor, a machine.*<br>
**Pre-conditions**: *Any conditions that need to be met before the information is sent*<br>
**Basic Flow**: *What is the usual workflow.*<br>
**Alternative Courses**: *Any workflow that differs from the above, it may be another way to the goal, or a different route for abnormal cases.*<br>
**Post Conditions**: *Any conditions that need to be met after the data is sent, e.g. indiction that the information has been sent.*<br>
**Exception Flows**: *Any conditions that need to result in a warning or an error.* 

---

The following may also be added in order to aid in the development of the assets. 
## Workflow Diagram
A diagram of the processes involved. This may be how each FHIR asset is related to each other, or the steps involved by a clinician. For creation of the diagrams https://app.diagrams.net/ is a free and easy to use app.

## Requirements
This should include any specific constraints and extensions to the profiles, and any codes, preferably using the SNOMED CT or dm+d system, that are to be used within the Profile or Extension.

## Asset Example

For every Profile and Extension within the UK Core there SHALL be an example alongside them to explain its use. For this reason, it is necessary that clinically sound information is given to be able to produce a usable example. This does not have to be in FHIR format and can be given after the structure of the asset has been agreed.

---
