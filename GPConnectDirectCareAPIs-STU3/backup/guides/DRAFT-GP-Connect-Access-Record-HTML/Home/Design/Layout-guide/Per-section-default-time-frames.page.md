## {{page-title}}

Date filtering is not applicable to all views and for those supporting date filtering it may not be applicable to all subsections.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fa fa-exclamation-triangle"></i> <b>Important:</b> Section default time frames to be reviewed following FoT feedback. A default time frame is only to be applied upon instruction by NHS Digital.
</div>

| Section | Section code | Subsections | Time frame |
| --- | --- | --- | --- |
| **Administrative items** | `ADM` | N/A | Consumer supplied |
| **Allergies and adverse reactions** | `ALL` | Current allergies and adverse reactions | N/A |
|     |     | Historical allergies and adverse reactions | N/A |
| **Clinical items** | `CLI` | N/A | Consumer supplied |
| **Encounters** | `ENC` | N/A | Consumer supplied |
| **Immunisations** | `IMM` | N/A | N/A |
| **Medications** | `MED` | Acute Medication (Last 12 Months) | All |
|     |     | Current Repeat Medication | All |
|     |     | Discontinued Repeat Medication | All |
|     |     | All Medication | Consumer supplied |
|     |     | All Medication Issues | Consumer supplied |
| **Observations** | `OBS` | N/A | Consumer supplied |
| **Problems and issues** | `PRB` | Active problems and issues | All |
|     |     | Major inactive problems and issues | Consumer supplied |
|     |     | Other inactive problems and issues | Consumer supplied |
| **Referrals** | `REF` | N/A | Consumer supplied |
| **Summary** | `SUM` | N/A | N/A |
| **Emergency Codes** | N/A | N/A | N/A |

<br>

The default time frame **MUST** be configurable in unit of month(s). It **MUST** be configurable by section (meaning, different sections can be configured with different defaults).

When a default time frame is applied at section level the following requirements **MUST** be adhered to:

*   any section/subsection listed in the table above with a time frame of ‘All’ **MUST** return all data regardless of the default time frame applied
*   any section/subsection listed with ‘Consumer supplied’ **MUST** only apply the default time frame when the consumer does not provide any date filter values
    *   a default date filter **MUST NOT** override a consumer supplied date filter value, meaning, the provider **MUST** return the full period as selected by the user
*   any section listed with a mix of ‘All’ and ‘Consumer supplied’ **MUST** apply the above requirements at the relevant subsection levels

When applying a default time frame the following messages **MUST** be supplied by the provider:

Subsection’s time frame ‘Consumer supplied’

```html
<div class="date-banner">
  <p> All data items from [SysDate – DefaultDatePeriod]</p>
</div>
```

Subsection’s time frame ‘All’

```html
<div class="date-banner">
  <p>Date filter not applied</p>
</div>
```

Provider systems **MUST** return a HTTP _Bad Request_ `400` error response if a date range is specified for a section that does not support filtering by a consumer supplied date range.