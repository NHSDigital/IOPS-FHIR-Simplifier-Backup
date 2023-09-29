### {{page-title}}


{{render:prescribing-continuous}}

Repeat prescribing (`continuous`) is valid for an authorised number of repeats or for a defined period. Prescription initiation is controlled by the prescriber. Each prescription issue is separately authorised by a prescribing clinician using their local prescribing system supported by any workflows or rules implemented for the repeat prescribing process.

The prescription authorisation results in an electronic prescription being sent to EPS. The repeat prescription is treated by the EPS in the same way as an `acute` prescription.

#### MedicationRequest and MedicationDispense Notes

{{render:erd-continous}}

{{render:prescribing-flowmodel-continuous}}

The concept of MedicationRequest with an intent of `plan` is described in [GP Connect Access Record Structured](https://digital.nhs.uk/developer/api-catalogue/gp-connect-access-record-structured-fhir)
The prescriber will add the following information in MedicationRequest resources.

- numberOfRepeatPrescriptionsAllowed in {{link:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation}}
- numberOfRepeatPrescriptionsIssued in {{link:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation}}

Dispensers should populate the following in MedicationDispense resources.

- numberofRepeatsAllowed in {{link:https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation}}
- numberOfRepeatsIssued in {{link:https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation}}
