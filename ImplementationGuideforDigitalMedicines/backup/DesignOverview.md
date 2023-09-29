# {{page-title}}

This section provides solution design guidance for the implementation of the medicines use cases using the FHIR standard.

There is not a one-size-fits-all solution for medicines interoperability. This guide describes the mandatory standards and likely differences within implementations and how the FHIR standard can be used in each.

Common adoption of the [NHS Dictionary of Medicines and Devices (dm+d)](NHSDictionaryofMedicinesandDevicesdmd) standard, including considerations for dose-based vs product-based prescribing, plus specific parts of the FHIR standard will result in nationwide interoperability of medicines data, between clinical systems and/or between Integrated Care Systems / Shared Medication Records.

Likely differences, and therefore design decisions, for any medicines interoperability solution will include the following.

### What are your target medicines data use cases?

Most care settings require a view of a patient's current medication and to build up this picture, data from different care settings needs to come together. The interoperability between clinical systems that support processes such as admission, transfer and discharge are equally as important as those systems that support the prescribing, dispensing, supply and administration of medicines.

See [Medications Data Use Cases](MedicationsDataUseCases).

### What is your high level architecture? Where are your medication records going to be persisted?

Are you implementating of a point-to-point interoperabilty solution between clinical systems, either in the same, or different organisations and/or care settings?

Are you implementating a shared record solution between multiple clinical systems either in the same, or different organisations and/or care settings? 

Are clinical systems going to maintain their own version of a patient's medication record?

Are clinical systems going to use a shared patient medication record, and will this be a shared copy or the single and only medication record used by the clinical system?

See [References Architectures](ReferenceArchitectures2).

---