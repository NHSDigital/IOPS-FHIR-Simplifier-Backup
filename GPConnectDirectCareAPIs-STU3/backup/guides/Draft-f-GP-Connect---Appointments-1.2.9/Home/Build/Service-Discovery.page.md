## {{page-title}}

## Determining which GP practice to book into ##

### Patient's registered practice ###

The "default" GP connect flow (as used in other capabilities) is shown in the diagram below, and includes the retrieval of the **ODS organisation code of the patient's registered practice** from PDS in step 1 (<span style="color: yellow; background-color: silver;">in yellow</span>).  For more details on this flow please see [Spine integration illustrated](https://developer.nhs.uk/apis/gpconnect-1-2-7/integration_illustrated.html).

{{render:gpconnect-appts-flow.png}}

This flow is suitable for Appointment Management consumers that wish to book into the patient's registered practice, but where an appointment is required at a different practice, an alternate mechanism for determining the practice and their ODS organisation code is needed.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note:</b> For a GP practice with multiple surgeries (locations), the ODS organisation code returned from PDS represents the GP practice organisation as a whole.  In order to determine the patient's preferred branch surgery please see <a href=https://simplifier.net/guide/pfs-appointments/home-build-branch-surgeries?version=current> Branch surgeries </a> for more information. </div>

### Booking into other practices ###

Where a GP Connect Appointment Management consumer wishes to book into a GP practice that is not the patient's registered practice, a different mechanism to discover the practice and their ODS organisation code is required.

#### Consumer system configuration ####

Appointment consumer systems that are predominantly used to book into GP practices within the local area (such as within a local federation) may use local system configuration to determine the ODS organisation code of the practice to book into.

For example a pre-configured pick list of organisations on the booking screen of the consumer screen allowing a user to choose which practice to book into.  The pick list may be configured by the consumer organisation or by the consumer system supplier in conjunction with the consumer organisation.

#### Directory of Services (DOS) - currently for UEC consumers only ####

Appointment consumer systems that are used to book into practices in a wider context where local knowledge of service availability cannot be relied on (such as 111 call centres that receive calls from across England) will need an enhanced mechanism for determining an appropriate practice to book the patient into, based on criteria such as:

- opening hours
- distance from patient
- service provision
- service availability to patient

The [Directory of Services](https://developer.nhs.uk/apis/uec-appointments/dos_overview.html) (DOS) is a service discovery and information tool for this purpose, and is currently being configured (June 2019) with GP Connect bookable services.

When booking into other practices, DOS replaces the function of PDS in determining the practice (and the practice's ODS organisation code) to book into.  However the PDS step is still required in order to verify the patient's NHS number.

{{render:gpconnect-appts-dos-flow.png}}

Please see the following pages from the Urgent and Emergency Care Appointment Booking specification for further information on integrating GP Connect Appointment UEC consumer systems with Directory of Services: 

- [DOS overview](https://developer.nhs.uk/apis/uec-appointments/dos_overview.html)
- [GP Connect workflow overview](https://developer.nhs.uk/apis/uec-appointments/gpc_wfoverview.html)
- [GP Connect workflow example](https://developer.nhs.uk/apis/uec-appointments/gpc_wfexample.html)
