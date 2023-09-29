## {{page-title}}

## Appointment API scope ##

The scope of appointment management is to deliver:

- <span class="label label-success">SELECTED</span> Functionality required for organisations to manage appointments on behalf of a patient.
- Functionality to view or manage an entire diary/appointment book.
- Functionality to create, amend, update diaries and/or schedules.

## New/unknown patients booking ##

The ability to create appointments for patients not known to the GP practice/diary owner:

- If a patient is not known to the local system the appointment boking will be rejected by booking system. It will not be possible to register the patient.
- <span class="label label-success">SELECTED</span> If a patient is not known to the local system the appointment booking will be rejected by booking system. It will be possible to register the patient via the GP Connect 'Register a Patient' API, and then use 'Book an Appointment'.
- If a patient is not known to the local system the appointment booking will be accepted and a patient record will be created with basic details about the patient (identifier).

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> Details of how to <a href=https://developer.nhs.uk/apis/gpconnect-1-2-7/foundations_use_case_register_a_patient.html> register a patient </a> can be found in the Foundations capability pack.</div>

## Access to available slots ##

When requesting the schedule of a particular diary, the level of detail returned should include:

- All booked appointments and available slots.
- Only slots that are available (all types).
- <span class="label label-success">SELECTED</span> Only slots that are available, have been marked/flagged as externally bookable via GP Connect and match the Booking Organisation Type and/or ODS Code and 'Embargo/Booking Window' rules.


## Search parameters ##

The following search parameters will be initially included:

- All available common (across all four systems) slot defining criteria such as Gender, Slot Type, Slot Length, complex date/time ranges.
- <span class="label label-success">SELECTED</span> Date Range,  Booking Organisation Type, Booking Organisation ODS Code, Urgent Care (UC) Disposition Code and Service ID, are accommodated to reflect more targeted Provider system slot availability and return.  Consumers can then apply further filtering and/or sorting at the client side. The last 2 are required to support the use of GP Connect APIs by UC Services.  

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> The Search Filter specification is flexible to allow for further search parameters to be defined. Value sets will be defined for these to be used by subsequent provider system slot access control.</div>


## Maximum time span of diaries returned ##

When searching for diaries, the results will be:

- Unlimited based on any timespan provided as part of the search.
- <span class="label label-success">SELECTED</span> Always be limited to a pre-defined maximum time period.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>A 2-week window was agreed with system suppliers as a reasonable trade-off between performance and usefulness initially, with the team seeking feedback from wider industry.</div>

## Do we need to use the 'AppointmentResponse' resource? ##

As per the suggested FHIR workflow in the [FHIR Appointment](https://simplifier.net/guide/pfs-appointments/g-p-a-h-f-a-a-a-p-profile-gpconnect-appointment-1-gpconnect-appointment-1?version=current) should the booking of an appointment utilise the 'AppointmentResponse' FHIR resource or are HTTP response codes sufficient for GP Connect use cases?

- AppointmentResponse resource will be provided in response to a booking request.
- <span class="label label-success">SELECTED</span> HTTP codes will be used to convey success/failure of a booking request.

## Patient dissent to share ##

<span class="label label-success">SELECTED</span> This is NOT to be applied in the context of the Appointment Management capability.

## Viewing and amending booked appointments ##

<span class="label label-success">SELECTED</span> This is only supported for future appointments, given the primacy of the administrative use case. Historic appointments should be considered part of the patient's medical record and therefore accessed via the Access Record HTML 'Encounters' view from the patient's registered GP practice. This assumes an update, according to usual business processes and external to GP Connect, by other GP practices hosting an appointment for the patient to their registered GP record. In the interest of simplicity and clarity in the specification, and taking into account the limited risks, the considered decision has been made that today's appointments will be classed as 'future'.

## Cancelling and amending booked appointments ##

What provision will be made for making changes to existing future appointments?

- Only cancellation will be allowed (must cancel and re-book).
- <span class="label label-success">SELECTED</span> Cancellation and amendments to the future Appointment Description and Comment are accommodated.
- Cancel and comprehensive amendments will be provisioned for (allowing appointments to move between slots/rescheduled).

Please note: Amending a cancelled appointment is not supported.

Are appointment amendments and/or cancellations only able to be made by organisations which booked them originally?

<span class="label label-success">SELECTED</span> Cancellation and amendments to future Appointment Description and Comment, can be made by any organisation participating in a GP Connect Appointment Management data-sharing agreement with the appointment hosting organisation.


## Tentative appointment booking ##

Is it possible to 'hold' an appointment slot obtained via GP Connect, and then confirm the booking at the end of a consultation/triage process?


<span class="label label-success">SELECTED</span> This functional requirement is not supported due to the additional technical complexity it would demand.  End-users will need to book the appointment then cancel if necessary, and good practice will need to be locally specified in business rules and policies agreed by participating organisations.  For example the practice of reserving numerous slots at the start of a '111' Urgent Care Call triage by using the 'Book Appointment' API, and then cancelling, would be considered bad practice and could contravene such agreements.

## Can appointments be rescheduled? ##

The API will not make provision for rescheduling of appointments in a single interaction as a result of the limitation on which data elements of an appointment can be amended.

Therefore, a consumer wishing to reschedule an appointment can do this through 2 API calls - firstly to cancel the existing appointment, then secondly to create a new appointment at the new date/time.

## Responsibilities in a federated booking context

Where there is a requirement for an implementation to provide an appointment management capability in a federated context, the GP Connect consumer implementation has the responsibility for defining the set of organisations which make up the federation. This consumer configuration will enable the consumer to make API calls to the relevant organisation set of endpoints in order to gain a federated view of appointments.

Neither the Spine Secure Proxy, nor the GP Connect provider will expose such federation configuration or expose any aggregated view of appointments for a federation.

Please refer to the [glossary](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms#federation) for a definition of a federation in this context.

## Branch surgeries

Please see [Branch surgeries](https://simplifier.net/guide/pfs-appointments/home-build-branch-surgeries?version=current) for more information GP Connect handling of branch surgeries, and implications for Appointment Management.
