---
topic: slot-availability-management
---

## {{page-title}}

There is a requirement to better ensure that the right appointment slots are made available to patients by:
  - enhancing the ability of provider organisations to control those appointments which can be booked by patients
  - ensuring that consumer system obtains only available appointments which are appropriate to patients
  - providing a more standardised categorisation of available appointment slots across provider systems so that inappropriate appointment booking is reduced
  - providing where applicable the GP branch surgery location of available appointment slots

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> The requirements below only apply for slot availability management so should only apply to {{pagelink:how-to-search-for-free-slots}} and {{pagelink:how-to-book-an-appointment}} but none of the other API use cases such as {{pagelink:how-to-retrieve-a-patients-appointments}}.
</div>

## Appointment availability control ##

Provider systems **SHALL**:
- enable provider system end users to designate the slots within their appointment books as 'PFS Appointments bookable'. This is a broad control to make slots in the appointment book available for booking through the (Patient Facing) Appointment Management FHIR API
- enable provider system end users to additionally specify which schedules/slots can be booked by a patient

The provider system end user **SHALL** be presented with an 'Organisation Type' list which reflects the [Organisation type](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-OrganisationType-1) valueset.

The consumer system **SHOULD** send their booking Organisation Type and booking organization ODS code in the `searchFilter` parameter, as specified in the {{pagelink:how-to-search-for-free-slots}} page, which the provider system will then use to determine the matching availability.

If the consumer system does not send any `searchFilter` parameters then the provider system will only return slots that are not restricted for booking to a patient.

The following table describes the matching rules for a provider system when applying the search filter passed by a consumer to the {{pagelink:how-to-search-for-free-slots}}  call:

<table>
  <thead>
    <tr>
      <th>Search filter sent by consumer</th>
      <th>Slots are returned that:</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>(no search filter)</td>
      <td>
      	&bull; Are marked as GP Connect bookable<br/>
      </td>
    </tr>
  </tbody>
</table>

## Booking window/embargo ##

It is recommended that provider systems also provide the functionality to enable the provider system end user to control how far in advance external organisations should be allowed to book slots and how near to the actual slot time - that is, via 'Booking Window' or 'Embargo' rules.

Where such rules have been set, provider systems **SHALL** only return slots which respect these rules.

## Appointment slot categorisation ##

Providers systems **SHALL** enable and require the mandatory selection by provider system end users of a 'Practitioner Role' and 'Delivery Channel' for schedules/slots as part of the end user GP Connect appointment configuration.

- the 'Practitioner Role' list **SHALL** reflect the [Practitioner Role](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-PractitionerRole-1) valueset
- the 'Delivery Channel' list **SHALL** reflect the [Delivery Channel](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-DeliveryChannel-1) valueset
- provider systems **SHALL** maintain alignment with the value sets
- these values **SHALL** NOT be configurable/modifiable by end users


## Branch surgery location ##

The Schedule resource has a mandatory 'Location' reference within the actor element. The referenced location **SHALL** be populated by provider systems with the name and address of the location where the appointment will take place. This will either be the GP practice where there are no branch surgeries OR the branch surgery.

See {{pagelink:branch-surgeries}}.