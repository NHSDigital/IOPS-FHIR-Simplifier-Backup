## {{page-title}}

Given the increasing need for cross-organisational appointment access, there is a requirement to better ensure that the right appointment slots are made available to the right external organisations by
  - enhancing the ability of provider organisations to control those appointments which can be booked by external organisations
  - ensuring that consumer organisations obtain only available appointments which are appropriate to them
  - providing a more standardised categorisation of available appointment slots across provider systems so that inappropriate appointment booking is reduced
  - providing where applicable the GP branch surgery location of available appointment slots

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b>The requirements below only apply for slot availability management so should only apply to <a href=https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current> Search for free slots </a> and <a href=https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-book-an-appointment?version=current> Book appointment </a> but none of the other API use cases such as <a href=https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-retrieve-a-patients-appointments?version=current> Retrieve a patient's appointments </a> or <a href=https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-amend-an-appointment?version=current> Amend an appointment </a>; for the latter the returned resources should reflect the complete organization appointment book.

## Appointment availability control ##

Provider systems SHALL:
- enable provider system end-users to designate the slots within their appointment books as 'GP Connect bookable'. This is a broad control to make slots in the appointment book available for booking through the GP Connect API
- enable provider system end-users to additionally specify which schedules/slots can be booked by an individual or list of organisations, and/or booking organisation type as well as enabling end-users to limit the number of slots which can be booked by this 'organisation access profile'.
- use ODS organisation codes as the organisation identifier for individual or lists of organisations used for appointment availability management

The provider system end-user SHALL be presented with an 'Organisation Type' list which reflects the [Organisation type](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-OrganisationType-1) valueset.

The consumer system SHOULD send their booking Organisation Type and booking organization ODS code in the `searchFilter` parameter, as specified in the [Search for free slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current) page, which the provider system will then use to determine the matching availability.

If the consumer system does not send any `searchFilter` parameters then the provider system will only return slots that are not restricted for booking to an individual or list of organisations, or by organisation type.

The following table describes the matching rules for a provider system when applying the search filter passed by a consumer to the [Search for free slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current)  call:

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
      	&bull; AND have no organisation type restriction set<br/>
      	&bull; AND have no organisation code (individual or list) restriction set
      </td>
    </tr>
    <tr>
      <td>
      	searchFilter<br/>
       	&nbsp; with organisation type set
      </td>
      <td>
      	&bull; Are marked as GP Connect bookable<br/>
      	&bull; AND have no organisation code (individual or list) restriction set<br/>
      	&bull; AND [<br/>
		&nbsp; &nbsp; &bull; have no organisation type restriction set<br/>
		&nbsp; &nbsp; &bull; OR have an organisation type restriction matching that passed in the searchFilter ]
      </td>
    </tr>
    <tr>
      <td>
      	searchFilter<br/>
       	&nbsp; with organisation code set
      </td>
      <td>
      	&bull; Are marked as GP Connect bookable<br/>
      	&bull; AND have no organisation type restriction set<br/>
      	&bull; AND [<br/>
		&nbsp; &nbsp; &bull; have no organisation code (individual or list) restriction set<br/>
		&nbsp; &nbsp; &bull; OR have an organisation code (individual or list) restriction matching that passed in the searchFilter ]
      </td>
    </tr>
    <tr>
      <td>
      	searchFilter<br/>
       	&nbsp; with organisation type set<br/>
       	&nbsp; and organisation code set
      </td>
      <td>
      	&bull; Are marked as GP Connect bookable<br/>
      	&bull; AND [<br/>
		&nbsp; &nbsp; &bull; have no organisation type restriction set<br/>
		&nbsp; &nbsp; &bull; OR have an organisation type restriction matching that passed in the searchFilter ]<br/>
      	&bull; AND [<br/>
		&nbsp; &nbsp; &bull; have no organisation code (individual or list) restriction set<br/>
		&nbsp; &nbsp; &bull; OR have an organisation code (individual or list) restriction matching that passed in the searchFilter ]
      </td>
    </tr>
  </tbody>
</table>

## Booking window/embargo ##

It is recommended that provider systems also provide the functionality to enable the provider system end-user to control how far in advance external organisations should be allowed to book slots and how near to the actual slot time - that is, via 'Booking Window' or 'Embargo' rules.

Where such rules have been set, provider systems SHALL only return slots which respect these rules.

## Appointment slot categorisation ##

Providers systems SHALL enable and require the mandatory selection by provider system end-users of a 'Practitioner Role' and 'Delivery Channel' for schedules/slots as part of the end-user GP Connect appointment configuration.

- The 'Practitioner Role' list SHALL reflect the [Practitioner Role](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-PractitionerRole-1) valueset.
- The 'Delivery Channel' list SHALL reflect the [Delivery Channel](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-DeliveryChannel-1) valueset.
- Provider systems SHALL maintain alignment with the value sets.
- These values SHALL NOT be configurable/modifiable by end-users.


## Branch surgery location ##

The Schedule resource has a mandatory 'Location' reference within the actor element. The referenced location SHALL be populated by provider systems with the name and address of the location where the appointment will take place. This will either be the GP practice where there are no branch surgeries OR the branch surgery.

Please see [Branch surgeries](development_branch_surgeries.html) for more information.