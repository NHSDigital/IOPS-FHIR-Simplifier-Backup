## {{page-title}}

## Determining which GP practice to book into ##

### Patient's registered practice ###

The 'default' Appointment Management flow is shown in the diagram below. It utilizes APIM (all steps in the blue container below are within the APIM system) to handle the discovery of the patient's GP in the 'Identify Routing' step of the diagram below. The patient's NHS number is provided via NHS App login. Both the NHS number and ODS code are then sent to the API producer.

{{render:apim-service-discovery}}

This flow is suitable for Appointment Management consumers that wish to book into the patient's registered practice, which is the only scenario supported in this release of Appointment Management.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note:</b> 
For a GP practice with multiple surgeries (locations), the ODS organisation code returned from PDS represents the GP practice organisation as a whole. To determine the patient's preferred branch surgery, see {{pagelink:branch-surgeries}} for more information. 
</div>

### Booking into other practices ###

Booking into other practices is not supported within this API. This may become available in future releases.

#### Consumer system configuration ####

Appointment consumer systems that are predominantly used to book into GP practices within the local area (such as within a local federation) may use local system configuration to determine the ODS organisation code of the practice to book into.

For example, a pre-configured pick list of organisations on the booking screen of the consumer screen allowing a user to choose which practice to book into. The pick list may be configured by the consumer organisation or by the consumer system supplier in conjunction with the consumer organisation.

