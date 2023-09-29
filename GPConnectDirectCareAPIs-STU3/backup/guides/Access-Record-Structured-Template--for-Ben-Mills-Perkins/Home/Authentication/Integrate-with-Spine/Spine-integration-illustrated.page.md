## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Illustration of the use of the GP Connect API showing all interactions required - both with Spine services and GP Connect endpoint API calls. 
</div>

## Spine integration required to consume GP Connect capabilities ##

GP Connect provider APIs are accessed through the NHS Spine. As such, consumers of GP Connect APIs are required to integrate with the following Spine services as a prerequisite to making API calls to GP Connect provider APIs:

- Personal Demographics Service (PDS)
- Spine Directory Service (SDS)
- Spine Secure Proxy (SSP)

## Overview

{{render: spineFlow.png}}

**Step 1. Personal Demographics Service**

A GP Connect consumer queries PDS for the patient in order to:

  - Verify the patient's NHS number
  - Retrieve the ODS organisation code of the patient's registered GP practice


For further details on this step please see the Personal Demographic Service page.

**Step 2. Spine Directory Service**

A GP Connect consumer queries SDS using the ODS organisation code retrieved in the previous step in order to retrieve:

  - The GP practice's GP Connect service root URL (their FHIR endpoint)
  - The GP practice's GP Connect ASID

For further details on this step please see the Spine Directory Services - overview and querying page.

**Step 3 onwards. Spine Secure Proxy**

A GP Connect consumer constructs a GP Connect FHIR request (incorporating the two items retrieved in the previous step), and sends it to the SSP.

The SSP then forwards the request on to the GP Connect provider system which returns its response back through to the SSP to the consumer system.  A number of GP Connect FHIR requests may be made in order to satisfy the full workflow of the capability.

For further details on this step please see the Spine Secure Proxy page.

Please see the full worked example below for the steps required to consume the GP Connect Appointment Management capability.

---

</br>