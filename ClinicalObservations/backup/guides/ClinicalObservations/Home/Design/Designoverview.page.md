---
parent: 
---
## Design overview

The Early Warning Score (EWS) specification allows the sending of just the total EWS score or the EWS score with parameter values or the EWS score, parameter values and their corresponding sub-scores.
The data that can be exchanged depends on the data available in the source system.

### Recommended option

The recommended option for sharing EWS information is to exchange the EWS score, the sub-score(s) and their associated vital signs observations.

The proposed FHIR design for the recommended option is shown below:

{{render:EWSdesign}}

The UK Core Observation profile carries the total score in its value element and the sub-score(s) in its component.value element. The base observations (carried in the UK Core Vital Signs profile) are linked to UK Core Observation via its derivedFrom element.

#### Assumption

The current design proposal assumes that there is no requirement to link the EWS sub-score directly to its base vital signs observation. This  assumption will be discussed with stakeholders.

#### XML example

 {{pagelink:TotalNEWS2ScoreSub-ScoresandObservationsBundleExample}} instance has been defined to illustrate this design.