## {{page-title}}

## Purpose ##

To meet strategic objectives to improve access to GP care, the Appointment Management API enables consumer system administrative and clinical end users to book and manage GP practice appointments held in any of the four GP principal practice systems. The implementation of the APIs within patient apps (to support patient direct access) is out of scope for initial deployment. Some API specification items may be uplifted in the future to reflect the requirements identified by related Appointment Management initiatives within the GP IT and Interoperability domains.

## Example scenarios ##

- administrative staff at a GP practice can book, view, amend or cancel appointments on behalf of a patient
- administrative staff at a GP extended access hub can book, view, amend or cancel appointments on behalf of a patient at any of its federated GP practices
- an urgent care (UC) 111 call centre handler or triage clinician can book, view, amend or cancel appointments on behalf of a patient at the patient's registered or federated GP practices or extended access hubs
- administrative staff and clinicians at a range of other care settings (for example, A&amp;E, physio, social and community services) will be able to book, view or cancel a GP appointment on behalf of the patient

## GP practice appointment slot availability ##

GP practices need to control access by external organisations to their appointment book. Provider systems will enable practice users to designate their schedules/slots as bookable by GP Connect, and by Organisation Type and/or specific Organisations ensuring that only slots matching the booking Organisation/Type are returned in response to a request.

The Appointment slots available via GP Connect will also be categorised by the end-user according to standardised values representing the role of the practitioner delivering the appointment, and the channel by which the appointment is to be delivered - for example, 'telephone', 'in-person'. This provides more information to the user booking the appointment on behalf of the patient, thereby reducing the risk of inappropriate appointment booking. The requirements are described in more detail in the [Slot availability management](https://simplifier.net/guide/pfs-appointments/home-design-slot-availability-management?version=current#Home-Design-Slot-Availability-Management) page.




## First of Type (FoT) care setting deployments ##

The following FoT deployments are being progressed:

### Care Setting 1: Within GP federations ###

Enabling a GP practice or appointment hub to book, view, amend or cancel a patient’s in-hours or extended hours appointments at the patient’s registered GP practice or another GP practice within the same [Federation](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms#federation).  

### Care Setting 2: From UC call centres to GP practices – in-hours, extended hours appointments ###
The requirement to support the use of the GP Connect capability for unscheduled care by UC services (UC call centres booking and managing appointments into GP practices) has been accommodated where possible in the API design. 
The call centre will retrieve and select in-hours or extended hours appointments for booking/managing at either: 

   - the patient’s registered GP practice

   - GP practices federated with the patient’s registered GP practice

   - a GP practice within the vicinity of the patient’s geographic location; for example, when the patient is on holiday

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> 
While the GP Connect programme primarily assumes that the appointment-hosting (provider) systems are the GP principal systems, the API technical design has accommodated the minimum viable features required to support booking and managing of appointments at UC providers such as Minor Injuries Units and GP out-of-hours services. This means that UC consumers will not need to use different APIs depending on the type of organisation they are targeting. 

This deployment care setting is currently out of scope for the GP Connect programme FoT deployments, which only incorporates assurance of the API fulfilment by the GP principal provider systems. The assurance and deployment of the APIs by UC provider systems will be progressed by NHS Digital Integrated Urgent Care programmes.</div>




## API definition ##

The following individual API calls are used by consumers to implement the Appointment Management capability:

- [Retrieve a patient's appointments](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-retrieve-a-patients-appointments?version=current#Home-Build-How-to-retrieve-a-patients-appointments)
- [Search for free slots](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current#Home-Build-How-to-search-for-free-slots)
- [Read an appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-read-an-appointment?version=current#Home-Build-How-to-read-an-appointment)
- [Book an appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-book-an-appointment?version=current#Home-Build-How-to-book-an-appointment)
- [Amend an appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-amend-an-appointment?version=current#Home-Build-How-to-amend-an-appointment)
- [Cancel an appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-cancel-an-appointment?version=current#Home-Build-How-to-cancel-an-appointment)

## Examples of consumer Appointment Management sessions

The use of the individual API calls listed above by consumers to fulfil business processes is illustrated with focus on the booking of an appointment. See [Appointment Management consumer sessions illustrated](https://simplifier.net/guide/pfs-appointments/home-design-appointments-consumer-sessions?version=current#Home-Design-Appointments-Consumer-Sessions).

## Profiled FHIR resources ##

See the [Appointment Management FHIR&reg; resources](https://simplifier.net/guide/pfs-appointments/home-build-fhir-resources?version=current#Home-Build-FHIR-Resources) page for details of the FHIR profiles used for the Appointment Management capability pack.

## Spine interactions ##

The Appointment Management capability message set includes the following set of Spine interactions:

| Operation                 | InteractionID             | 
|---------------------------|---------------------------| 
| [Get organisation schedule](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-search-for-free-slots?version=current#Home-Build-How-to-search-for-free-slots) | `urn:nhs:names:services:gpconnect:fhir:rest:search:slot-1` |
| [Read appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-read-an-appointment?version=current#Home-Build-How-to-read-an-appointment)          | `urn:nhs:names:services:gpconnect:fhir:rest:read:appointment-1` |
| [Create appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-book-an-appointment?version=current#Home-Build-How-to-book-an-appointment)        | `urn:nhs:names:services:gpconnect:fhir:rest:create:appointment-1` |
| [Amend appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-amend-an-appointment?version=current#Home-Build-How-to-amend-an-appointment)         | `urn:nhs:names:services:gpconnect:fhir:rest:update:appointment-1` |
| [Cancel appointment](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-cancel-an-appointment?version=current#Home-Build-How-to-cancel-an-appointment)        | `urn:nhs:names:services:gpconnect:fhir:rest:cancel:appointment-1` |
| [Get patient appointments](https://simplifier.net/guide/PFS-Appointments/Home/Build/How-to-retrieve-a-patients-appointments?version=current#Home-Build-How-to-retrieve-a-patients-appointments)  | `urn:nhs:names:services:gpconnect:fhir:rest:search:patient_appointments-1` |


## Implementation and testing ##

Below is the suggested order in which the appointment capabilities should be implemented as a provider supplier. The specified order has been recommended around the functionality of the GP Connect Automated Test Suite and any internal dependencies between the test scenarios for the different Appointment Management endpoints. The Appointment Management capability test scenarios are dependent on the foundation capabilities and therefore the foundation endpoints should be developed and tested before implementing the Appointment Management capabilities.

It’s recommended that you develop against the Automated Test Suite as this will help with creating a GP Connect compliant product. By implementing the endpoints in the order below, the Automated Test Suite set of tests for that endpoint can be run during development without you seeing errors due to pre-test API calls or post-test validation API calls relevant to the test being run and failing as they have not been developed yet.

| Order | API endpoint | Test suite endpoint dependencies | Reason for dependency |
| ------------- | ------------- | ------------- | ------------- |
| #1 | Search for free slots | Read an organization / Read a practitioner / Read a location | The `Search for free slots` test scenarios require some of the foundation endpoints to validate references within returned resources contained within the response bundle. |
| #2 | Book an appointment | Register a patient / Find a patient / Search for free slots / Read an organization / Read a location / Read a practitioner / Read a patient | The `Book an appointment` endpoint finds a slot which it then uses to book an appointment for a known patient. To find the logical IDs of the elements required to book an appointment it requires the `Find a patient` and `Search for free slots` endpoints to have been implemented and working. Some of the tests also require the `Register a patient` endpoint to have been implemented as it tests booking an appointment against a GP Connect temporary patient. |
| #3 | Retrieve a patient’s appointments | Search for free slots / Find a patient / Book an appointment / Register a patient / Read an organization / Read a location / Read a practitioner / Read a patient | The test suite builds the appointments for a patient before testing the `Find a patient’s appointments` capability to make sure appointments exist to find. This requires the endpoints to find free slots, find a patient’s logical identifier, book an appointment and, in some tests, create a temporary patient against which to book the appointment. |
| #4 | Amend an appointment | Search for free slots / Find a patient / Book an appointment / Register a patient / Read an organization / Read a location / Read a practitioner / Read a patient | The test scenarios for the `Amend an appointment` capability require most of the foundation endpoints and most of the other appointment endpoints to be implemented to find or create the appointments which the tests are going to update as part of the `Amend an appointment` tests. |
| #5 | Cancel an appointment | Search for free slots / Find a patient / Book an appointment / Amend an appointment / Register a patient / Read an organization / Read a location / Read a practitioner / Read a patient | The test scenarios for the `Cancel an appointment` capability require most of the  foundation endpoints and the other Appointment Management endpoints to be implemented in order to find, create and amend the appointments required for the test scenarios and validation of the returned response. |
| #6 | Read an appointment | Search for free slots / Find a patient / Book an appointment / Amend an appointment / Cancel an appointment / Register a patient / Read an organization / Read a location / Read a practitioner / Read a patient | The test scenarios for `Read an appointment` require different foundation endpoints and all the other appointment endpoints to be implemented as the tests need to create appointments with different statuses if they are not available. The test must find the local identifiers for both the appointment it is trying to read and any steps it may need to do to create or validate the appointment. |
