## {{page-title}}

In FHIR, it allows the use of a flag titled 'Must support' to be attached to any give data item. The FHIR specification states, "The meaning of "support" is not defined by the base FHIR specification, but can be set to true in a profile. When a profile does this, it **SHALL** also make clear exactly what kind of "support" is required".

In the GP Connect FHIR profiles, we have used the 'Must support' flag to represent the required data items as described above.

This leads to our definition for use in GP Connect:

**Must support** = if a system is providing resources and one of the items is flagged as 'Must support' the system **MUST** include the data item if it is available to be sent.
