## {{page-title}}

Patient consent
How are patient consent preferences dealt with?

- <span class="label label-success">SELECTED</span> patient consent enforced by the provider system and cannot be overridden
- patient consent enforced by the provider but can be overridden by consumer

<span class="label label-info">DECISION</span> Patient consent enforced by the provider system MUST be adhered to when returning a patient record.

### Patient data exclusions
What patient data exclusions are associated with Access Record HTML?

These can be determined by two potential sets of exclusion settings:

- manual exclusion (based on explicit patient preference)
    - <span class="label label-success">SELECTED</span> provider system-based patient preferences
    - Summary Care Record (SCR) standard patient preferences (in addition)^1^
- automatic exclusion (based on implied patient preference)^2^

^1^ Providers are not initially expected to enforce SCR patient preferences in relation to returning API data. They MUST only respect their own principal patient preferences.

^2^ Automatic or inferred exclusions are not supported as this would be technically impractical (it’s not possible to filter out all free-text and other fields which could potentially contain data which should ideally be excluded).

<span class="label label-info">DECISION</span> Provider system MUST enforce exclusion rules, either for the complete patient record, or sections/data-items.

### ‘Confidential’ (GP practice-designated) data exclusions
How are ‘confidential’ data items dealt with?

- <span class="label label-info">DECISION</span> provider system MUST enforce exclusion rules, either for the complete patient record, or sections/data-items
- <span class="label label-info">DECISION</span> items designated by the practice as confidential MUST NOT be provided, and processed in the same way as patient data exclusions

### Sensitive data exclusion set
How are sensitive data items dealt with?

<span class="label label-info">DECISION</span> Provider API processing MUST support the application of an exclusion set, which MUST be configurable, including containing null values. The current Royal College of General Practitioners (RCGP) sensitive exclusion set MUST be applied, for the complete patient record, or sections/data-items, but is likely to amended pending future guidance and review (to be approved by the Joint GP IT Committee (JGPIT)).
GP summary exclusion code Lists

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fas fa-exclamation-circle text-primary"></i> <b>Information:</b> You will need to register for an account on TRUD (the NHS Terminology Reference Data Update Distribution Service) in order to view the above link.
</div>

### Data sharing agreements

What data sharing agreements need to be in place?

- <span class="label label-info">DECISION</span> data-sharing agreement must be in place between the consuming organisation and the providing organisation
- <span class="label label-info">DECISION</span> the Spine Security Proxy validates this requirement

Therefore, provider systems MUST NOT apply or change locally-configured data-sharing validation.

### Exclusion warnings
How are exclusion warnings identified within Access Record HTML?

- no indication that data has been excluded
- <span class="label label-success">SELECTED</span> warning indication per section that data has been excluded (within the time frame)
- <span class="label label-success">SELECTED</span> in line with some information related to the data item
that is, encounter date/time but not the place or encounter details

<span class="label label-info">DECISION</span> Warning needed that data supplied for a patient may be incomplete/withheld due to patient preferences, GP practice designation of ‘Confidential’ or as a result of the application of the sensitive exclusion set - to be displayed both within the section banner as well as at line item level.