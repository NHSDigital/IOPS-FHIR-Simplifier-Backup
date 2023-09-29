## {{page-title}}

## FHIR resources when searching for free slots ##

This diagram shows the relationships between FHIR resources used when searching for free slots to book.

{{render:ResourceRelationshipsStructure.png}} 

<br />

The FHIR resources above are used in the following API interactions:

### Search for free slots ###

View {{pagelink:how-to-search-for-free-slots}}.

##### Request #####

*No FHIR resource is sent within the request payload.*

##### Response #####

- [FHIR Bundle](https://www.hl7.org/fhir/STU3/bundle.html), populated with:
  - [GPConnect-Slot-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Slot-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html))
  - [GPConnect-Schedule-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Schedule-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/schedule.html))
  - [CareConnect-GPC-Location-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Location-1) (based on [FHIR Location](https://www.hl7.org/fhir/STU3/location.html))
  - [CareConnect-GPC-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Practitioner-1) (based on [FHIR Practitioner](https://www.hl7.org/fhir/STU3/appointment.html))
  - [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/appointment.html))

---

## FHIR resources when booking and managing booked appointments ##

This diagram shows the relationships between FHIR resources used when booking an appointment or managing a booked appointment.

![Diagram - Appointment resource relationship structure](images/appointments/appointment-fhir-resources-appointment.png)

<br/>

The Appointment resource and Organization resource (used to hold the booking organisation) are used in the request and/or response payloads of the API interactions below.  References to the other resources (such as Slot, Location, Patient, and so on) are populated in the relevant fields of the Appointment resource.

### Retrieve a patient's appointments ##

View {{pagelink:how-to-retrieve-a-patients-appointments}}.

##### Request #####

*No FHIR resource is sent within the request payload.*

##### Response #####

- [FHIR Bundle](https://www.hl7.org/fhir/STU3/bundle.html), populated with:
	- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
		- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))

### Read an appointment ###

View {{pagelink:how-to-read-an-appointment}}.

##### Request #####

*No FHIR resource is sent within the request payload.*

##### Response #####

- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
	- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))


### Book an appointment ###

View {{pagelink:how-to-book-an-appointment}}.

##### Request #####

- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
	- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))
##### Response #####

- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
	- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))

### Cancel an appointment ###

View {{pagelink:how-to-cancel-an-appointment}}.

##### Request #####

- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
	- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))

##### Response #####

- [GPConnect-Appointment-1](https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-Appointment-1) (based on [FHIR Appointment](https://www.hl7.org/fhir/STU3/appointment.html)), with a contained resource of:
	- [CareConnect-GPC-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1) (based on [FHIR Organization](https://www.hl7.org/fhir/STU3/organization.html))

---

## FHIR resources returned in error responses ##

If an error occurs during the processing of the request in any of the above API interactions, the provider system will return an HTTP error code along with an OperationOutcome resource in the response payload. See {{pagelink:error-handling}}.

##### Response #####

- [FHIR OperationOutcome](https://www.hl7.org/fhir/STU3/operationoutcome.html)

---


