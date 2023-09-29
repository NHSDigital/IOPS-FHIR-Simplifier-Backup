## {{page-title}}

The term 'filing' essentially means where the data is stored within the patient record within the supplier system. For example, the information relayed in the FHIR `CareConnect-GPC-Encounter` profile may sit within the `Consultations` section of a supplier system.

### Auto-filing

The term 'auto-filing' relates to the automatic placement of information into the patient record, with no interaction from a human whatsoever.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: There is no intention of auto-filing any payloads at this time.
</div>

However, auto-filing could one day be achieved, providing the data model between care settings is agreed, consistent, and contains the necessary information for 'rules' to be applied as to whether clinical engagement is required.

It is expected that these rules would be configured at a local organisation-level, and would consider the following:

- <b>Who</b> sent the payload?
- <b>What</b> information has been sent?
- <b>Why</b> did they send it?