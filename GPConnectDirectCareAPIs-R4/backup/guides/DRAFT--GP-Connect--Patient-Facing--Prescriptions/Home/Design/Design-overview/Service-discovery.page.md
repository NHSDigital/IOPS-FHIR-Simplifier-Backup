## {{page-title}}

The default Prescription Management flow is shown in the diagram below. It utilizes APIM to handle the discovery of the patient's GP in the 'Identify Routing' step. The patient's NHS number is provided via NHS App login. Both the NHS number and ODS Code are then sent to the API producer.

{{render:apim-service-discovery}}

This flow is suitable for Prescription Management consumers that want to view medication or manage a medication order.

<div markdown="span" class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i>
<b>Note:</b> For a GP practice with multiple surgeries (locations), the ODS organisation code returned from PDS represents the GP practice organisation as a whole. </div>
