## {{page-title}}

Consultations are one of the most important forms in which structured clinical information is recorded in the patient records within GP systems.

However, there is no standard structure or format for recording consultations that is common across all systems.

This presents a challenge in developing a common set of FHIR profiles that are capable of representing the consultation structures that exist within participating systems.

It is also a challenge for provider systems in expressing native consultations in a standardised form as well as being a challenge for consumers in understanding those structures.

It is important to define what we mean by consultation. Not all clinical information is recorded consistently across systems within structures that can be classed as consultations. Therefore, it is important to note that a consultation-oriented query alone will not return all of the clinical information held within a patient record.

This page is designed to address these challenges:

- it provides a clear definition of what is meant by consultation in the context of the current set of participating provider systems
- it identifies the limitations of consultation-based queries in isolation as a method for retrieving all elements of patient records
- it describes the set of consultation structures available in provider systems and guidance for populating the FHIR resources required to represent these structures in a consistent manner that is processable by consumers
- it provides guidance for consumer systems processing the FHIR resources representing consultation structures on source systems as to the variances between representations and the correct handling of these structures

---