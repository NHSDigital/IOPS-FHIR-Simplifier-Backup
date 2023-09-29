## {{page-title}}

## Appointment API scope ##

The scope of (Patient Facing) Appointment Management is to deliver:

- functionality required for patients to create, cancel or view their own appointments at their GP

## Access to available slots ##

When requesting the schedule of a particular diary, the level of detail returned should include:

- only slots that are available, have been marked/flagged as externally bookable via this APIs and match the 'Embargo/Booking Window' rules


## Search parameters ##

The following search parameters will be initially included:

- Date Range,  Booking Organisation Type, Booking Organisation ODS Code, Urgent Care (UC) Disposition Code and Service ID are accommodated to reflect more targeted provider system slot availability and return.  Consumers can then apply further filtering and/or sorting at the client side. The last 2 are required to support the use of GP Connect APIs by UC Services.  

<div class="alert alert-info" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> The Search Filter specification is flexible to allow for further search parameters to be defined. Value sets will be defined for these to be used by subsequent provider system slot access control.
</div>

## Maximum time span of diaries returned ##

When searching for diaries, the results will be:

- always be limited to a predefined maximum time period

<div class="alert alert-info" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> A 2-week window was agreed with system suppliers as a reasonable trade-off between performance and usefulness initially, with the team seeking feedback from wider industry.
</div>

## Do we need to use the 'AppointmentResponse' resource? ##

As per the suggested FHIR workflow in the {{pagelink:Home/FHIR-Assets/All-Assets}} should the booking of an appointment utilise the 'AppointmentResponse' FHIR resource or are HTTP response codes sufficient for GP Connect use cases?

- HTTP codes will be used to convey success/failure of a booking request

## Patient dissent to share ##

This is NOT to be applied in the context of the (Patient Facing) Appointment Management FHIR API.

## Viewing booked appointments ##

- for patient-facing services - supported for both past and future appointments to mirror current functionality in IM1 

## Cancelling booked appointments ##

What provision will be made for making changes to existing future appointments?

- cancellation of future appointments are accommodated

## Tentative appointment booking ##

Is it possible to 'hold' an appointment slot obtained via GP Connect, and then confirm the booking at the end of a consultation/triage process?

This functional requirement is not supported due to the additional technical complexity it would demand. End users will need to book the appointment, then cancel if necessary, and good practice will need to be locally specified in business rules and policies agreed by participating organisations. For example, the practice of reserving numerous slots at the start of a '111' Urgent Care Call triage by using the 'Book Appointment' API, and then cancelling, would be considered bad practice and could contravene such agreements.

## Can appointments be rescheduled? ##

The API will not make provision for rescheduling of appointments in a single interaction. The must be cancelled and rebooked.

Therefore, a consumer wishing to reschedule an appointment can do this through 2 API calls - firstly to cancel the existing appointment, then secondly to create a new appointment at the new date/time.

## Responsibilities in a federated booking context

Where there is a requirement for an implementation to provide an appointment management capability in a federated context, the GP Connect consumer implementation has the responsibility for defining the set of organisations which make up the federation. This consumer configuration will enable the consumer to make API calls to the relevant organisation set of endpoints in order to gain a federated view of appointments.

The GP Connect provider will not expose such federation configuration or expose any aggregated view of appointments for a federation.

See the [glossary](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms#federation) for a definition of a federation in this context.

