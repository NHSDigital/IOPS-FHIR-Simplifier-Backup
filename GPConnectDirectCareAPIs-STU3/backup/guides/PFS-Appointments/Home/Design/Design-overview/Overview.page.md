## {{page-title}}

## Purpose ##

To meet strategic objectives to improve access to GP care, this API enables patients (via a consumer application) to book and manage GP practice appointments. The implementation of non-patient access is out of scope for this deployment, and is covered by the previous iteration: [GP Connect Appointment Management API](https://developer.nhs.uk/apis/gpconnect-1-2-7/appointments.html). Some API specification items may be uplifted in the future to reflect the requirements identified by related Appointment Management initiatives within the GP IT and Interoperability domains.

## Example scenarios ##

- a patient can book, view or cancel appointments

## GP practice appointment slot availability ##

GP practices need to control access by external organisations to their appointment book. Provider systems will enable practice users to designate their schedules/slots as bookable, ensuring that only slots available for direct patient booking are returned in response to a request.

The appointment slots available will also be categorised by the end user according to standardised values representing the role of the practitioner delivering the appointment and the channel by which the appointment is to be delivered - for example, 'telephone', 'in-person'. This provides more information to the patient booking the appointment, thereby reducing the risk of inappropriate appointment booking. The requirements are described in more detail in {{pagelink:Home/Design/Interactions/Slot-availability-management.page.md}}.

## First of Type (FoT) care setting deployments ##

The following FoT deployments are being progressed:

### Care Setting 1: Within GP federations ###

Enabling a patient to book, view or cancel in-hours or extended hours appointments at the patient’s registered GP practice or another GP practice within the same [federation](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms#federation).  

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note:</b> 
The GP Connect (Patient Facing) Appointment Management programme primarily assumes that the appointment-hosting (provider) systems are GP principal systems. Other provider systems (such as minor injuries units, and GP out-of-hours services) are out of scope.
</div>


## API definition ##

The following individual API calls are used by consumers to implement this API:

- {{pagelink:how-to-retrieve-a-patients-appointments}}
- {{pagelink:how-to-search-for-free-slots}}
- {{pagelink:how-to-read-an-appointment}}
- {{pagelink:how-to-book-an-appointment}}
- {{pagelink:how-to-cancel-an-appointment}}

## Examples of consumer Appointment Management sessions

The use of the individual API calls listed above by consumers to fulfil business processes is illustrated with focus on the booking of an appointment. See - {{pagelink:appointment-consumer-sessions}}.

## Profiled FHIR resources ##

See - {{pagelink:Home/FHIR-Assets/All-Assets}} for details of the FHIR profiles used for this API.