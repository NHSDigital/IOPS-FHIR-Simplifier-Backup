## {{page-title}}

The provider **MUST** return banner messages as described in this section. The consumer system **MUST** present the banner messages as returned by the provider system.

### GP transfer banner

In the scenario where the patient’s GP record is not ‘fully integrated’ into the ‘new’ GP, following a GP transfer, then only data entered to the new GP’s record **MUST** be provided. A warning message stating that the record is either not available (no data entered to the new GP record), or incomplete due to the transfer, **MUST** be provided and displayed. The message **MUST** include the date that the data has been excluded from. Set dd-Mmm-yyyy to the date the patient registered at their new GP practice.

```html
<div class="gptransfer-banner">
  <p>Patient record transfer from previous GP practice not yet complete; information recorded before dd-Mmm-yyyy may be missing</p>
</div>
```
### Content banners

The content banner **MUST** be used by the provider to detail any specific business rules applied to the section content which is not standard across providers, or any non-compliance with the specification due to constraints of their GP system.

#### Subsection content banner

Any content descriptions for a subsection **MUST** be applicable to that subsection only. Where the content description applies to more than one subsection (but not all), it **MUST** be repeated in the applicable subsections. A subsection content description **MUST NOT** be replicated as section content.

### Date banner

A date banner **MUST NOT** be returned for sections which do not support a date filter. See individual HTML views for section date filters supported. For sections which support date filters, the following date banners **MUST** be returned as applicable.

#### Applied date ranges

Provider systems **MUST** return the consumer date range applied to a section’s data, where applicable, beneath the section/subsection header.

If consumer start date and end date applied:

```html
<div class="date-banner">
  <p>For the period 'dd-Mmm-yyyy' to 'dd-Mmm-yyyy'</p>
</div>
```
If no consumer end date applied:

```html
<div class="date-banner">
  <p>Data items from [Start Date]</p>
</div>
```

If no consumer start date applied:

```html
<div class="date-banner">
  <p>Data items until [End Date]</p> 
</div>
```

#### Not applied date ranges

In the event of a consumer date range being applied to a section, subsections not supporting a date filter **MUST** display the following:

```html
<div class="date-banner">
  <p>Date filter not applied</p> 
</div>
```
The purpose of this message is to make clear that a consumer specified date filter has not been applied to the subsection(s), which does not support date filters.

#### Default date ranges

Where the consumer system has not supplied a date range for a section which supports date filters, and while the default is for **ALL** items to be provided, the following message **MUST** be supplied by the provider beneath the section/subsection header.

```html
<div class="date-banner">
  <p>All relevant items</p>
</div>
```

### Section exclusion banner

Exclusions may be applied to the section/subsections in various circumstances. Where any exclusions have been applied a message banner **MUST** be included. As shown in the layout, the exclusion banner will only be included against the specific table where exclusions have been applied. Therefore, it will only be at section level where it is a single table section.

The following message **MUST** be supplied by the provider if any items were excluded for these reasons:

```html
<div class="exclusion-banner">
  <p>Items excluded due to confidentiality and/or patient preferences</p>
</div>
```