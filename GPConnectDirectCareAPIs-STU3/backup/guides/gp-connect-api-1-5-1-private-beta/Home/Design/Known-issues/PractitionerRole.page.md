## {{page-title}}

There is an issue with the PractitionerRole resource in the base FHIR® specification. It occurs in GP Connect when a practitioner has more than one PractitionerRole associated with them and both are returned in the same bundle.

An example of where this happens would be if a list of medications contained two medications that were prescribed by the same practitioner:

1. Medication 1, prescribed by Practitioner at Practice A
2. Medication 2, prescribed by Practitioner at Out of Hours service B

Two PractitionerRole resources would be created that both relate to the same practitioner. However, as the MedicationRequest resource only references the practitioner and not PractitionerRole it will be impossible to ascertain which PractitionerRole relates to which medication.

This issue may occur for any profile where there is a reference to Practitioner rather than PractitionerRole

As a workaround for this issue, in GP Connect when providing responses to queries systems **MUST** only supply 1 PractitionerRole per practitioner. If more than one should exist then the system **MUST NOT** supply any.