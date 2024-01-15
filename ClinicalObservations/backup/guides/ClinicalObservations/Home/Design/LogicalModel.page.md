---
parent: 
---
### Logical Model

This is the draft logical model for Clinical observations it has not been approved or reviewed in any way and is for discussion only. 

This model represents a DCM (Detailed Clincial Model) of the data items required to exchange Observation information either are individual observation resources or as part of early warning scores such as NEWS2 and PEWS. The model is a FHIR logical model which means it uses the FHIR datatypes and structures. It does not include exchange specific resources such as message headers. If also currently does not include LOINC coding required for compliancy with the FHIR standard for vital signs. This will be added in a later interation of the model.

There are numerous issue with coded items some of which require SNOMED CT and clinical input to resolve most of which are highlighted in the model. Some examples are:
- Representation of Nurse concern which is not supported in SNOMED CT and Parent concern difficult to model as may not be supported in SNOMED CT. Currently modelled as a patient condition observation with related person as performer and value element for same / worst. If this is correct then can nurse(is it just nurse) concern be modelled in a similar way.
- Patient on Oxygen or air may not not supported in SNOMED CT
- Patient consciousness requires input of how to code the observation and values 
- Some parts of the model which have been modeled as separate observations may be able to be merged for example BMI and Centile BMI. 
- All coding will need reveiw by SNOMED CT SME for correctness of concepts used and display name alignment with SNOMED CT preferred terms.

{{tree:https://fhir.nhs.uk/StructureDefinition/ClinicalObservationsDataSet}}


