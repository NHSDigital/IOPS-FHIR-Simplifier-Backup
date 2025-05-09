## {{page-title}}

This page summarises the release notes for previous versions.

---

## 0.7.4 changes ##

### Access to deceased patient's record  ###

**Description:**

- Added design guidance for providers to allow access to deceased patient's records
- Added deceased date time to the list of demographics used for cross checking
- Updated request validations and requirements for response body

### Update to error handling for query for a deceased patient's record  ###

**Description:**

- Updated error handling to specify that provider should return error code "PATIENT_NOT_FOUND" when a query for a deceased patient is received after the allowed access period.

---

## 0.7.3 changes ##

### Emergency Codes section added to Access Record HTML view in 0.5.3 and 0.7.3  ###

**Description:**

- Emergency codes section added to the top of the Summary view
- New page created to specify the layout and functionality of the Emergency Codes view

### Consumer limitations set for some healthcare settings / roles  ###
This change does not impact technical delivery of the API and as such NHS Digital have chosen not to uplift the version number of the specification to avoid confusion with Supplier delivery and compliance.

**Description:**

- Added bullet point to the information governance principles to require consumers to apply role based access controls in support of direct care access and to ensure any limitations to the extent of access for their healthcare setting or user roles is applied e.g. limitating some users to a subset of the HTML views
- Removed references to first of type in the information governance principles to bring it up to date
- Strengthened note on the HTML introduction for consumers to meet the IG and clinical safety requirements
- Added note to the implementation guidance section retrieval section to note need to meet IG principles in controlling access to the views required or permitted by user roles

---

## 0.7.2 changes ##

### Migrate core changes from 1.2.3 into 0.5.2 and 0.7.2 ###

**Description:**

- Grouping of git issues raised to contain all the necessary changes required in 0.7.2 to align with changes made in 1.2.3, listed below:

#### Minimise likelihood of rejected tokens due to clock skew ####

**Description:**

- When determining validity of the JWT token, clock skew between consumer and provider may cause a token to be rejected.

- The following addition has been made:

  - Providers and consumers must synchronise their system clocks with NTP time servers

- The following related clause has been added as was not previously explicitly stated:

  - Providers must reject tokens that have expired (validate the `exp` element)

- Please note: `iat` should not be validated by providers


#### Clarify ASID requirements and topologies for "aggregators" ####

**Description:**

- Clarify that GP Connect consumer systems must have a unique ASID per organisation using the consumer system
- Where GP Connect consumer applications are hosted or provisioned by another organisation, the ASID sent in the `Ssp-From` header, and the `requesting_organization` resource sent in the JWT must reflect the organisation from where the request originated, rather than the hosting organisation

#### SDS query changes to support multiple consumers at a site ####

**Description:**

- Update SDS queries used by a consumer to locate a provider's FHIR service root URL

  - Instead of querying the AS record first, query the MHS record first

  - Only provider systems hold GP Connect interaction IDs on their MHS record, this enables the new queries to return the providers endpoint deterministically

- Adding information where a consumer system wants to lookup it's own ASID

#### Consumer shall not amend the Provider service root URL as retrieved from SDS ####

**Description:**

- When a consumer systems construct a full URL to be sent to the SSP, they must not amend any part of the provider service root URL, except for prefixing with the SSP URL, and suffixing with the FHIR request path

- The following examples will cause the SSP to reject the request:
  - Changing the provider's hostname to an IP address
  - Adding an explicit `:443` port declaration where none exists in SDS

#### Improve clarity of JWT population page for new consumers *(cosmetic)* ####

**Description:**

- Clarifications to JWT population guidance for consumers
- Improved formatting and layout

#### Change spec name of "GP Connect" to "GP Connect API"  *(cosmetic)* ####

**Description:**

- Specification name has changed from GP Connect to GP Connect API to maintain consistency with release of GP Connect Messaging specification

## Foundations ##

### Update Conformance Profile version ###

**Description:**

- Update version number in Conformance Statement to 0.7.2

## Access Record HTML ##

### HTML Implementation Guidance Layout - Change Multi-table example ###

**Description:**

The multiple table example in the layout section of the HTML Implementation Guide uses the Problems and Issues view and shows 2 subsections.

The Problems and Issues view was changed from 2 subsections in v0.7.0 to having 3 sections in v0.7.1.

The example has been update to reflect this.

### Change warning message for patient transfers ###

**Description:**

Patient transfer banner message changed from:

*Patient record transfer from previous GP practice not yet complete; any information recorded before dd-Mmm-yyyy has been excluded*

to:

*Patient record transfer from previous GP practice not yet complete; information recorded before dd-Mmm-yyyy may be missing*

### Observations view does not include requirement for units of measure ###

**Description:**

More information provided to support the requirement for units of measure in Observations.

Requirement added to Implementation standards page to support displaying units where available.

### Updated Applied date ranges date banner text to remove word **all** ###

**Description:**

Feedback from providers resulted in the removal of the word **all** from:

All data items from [Start Date]

All data items until [End Date]

to:

Data items from [Start Date]

Data items until [End Date]

---

## 0.7.1 changes ##

### ARHTML Medications - Minor alterations to wording ###

**Description:**

- a number of minor uplifts following review

### Specify layout for Summary view in accordance with implementation guide for other views ###

**Description:**

- the Implementation Guide gives detailed instructions for the layout of the views where they are single or multiple table views, but this excludes the Summary view and cross references the HTML definition for the Summary view

### Provide additional guidance for display of numbers with decimal places ###

**Description:**

Guidance has been provided for the display of numeric values to decimal places for medication items and included in the observations specification for the numeric values for such test and measurement results.

This states "Do not put a trailing zero after a sub-decimal value (that is, '0.5' is correct but '0.50' is incorrect)".

### Rules for provider return when default date range is not all items ###

**Description:**

The specification supports application of a default date range, but the specification does not include the business rules for applying a default date range other than where the default is ALL items.

The specification should include rules and date banner message definitions for an applied default date range.

### Uplift specification to include guidance on Controlled Drugs ###

**Description:**

Controlled drugs need to be flagged as such at the line item level as this is clinically relevant supporting information.

The specification should include rules and date banner message definitions for an applied default date range.

### Revise Medication headings  ###

**Description:**

- Change the following headings (and reference to the headings)
  - Recent Acute Medication > Acute Medication (Last 12 Months) applies to Summary and Medications view
  - All Medication (Summary) > All Medication applies to Medications view only

### Separate Major Inactive Problems and Issues into a separate subsection ###

**Description:**

The clinical importance of significant past problems has been raised. This information is sufficiently important to be included in the Summary view. The problems and issues view therefore requires uplifting to separate the content of the inactive problems and issues into two subsections

 - Major Inactive Problems and Issues
 - Other Inactive Problems and Issues

Supporting definition of major to be included along with definitions for handling no significance for individual records or provider systems not supporting significance levels which meaningfully translate to Major / Minor

### Add Major Inactive Problems and Issues to the Summary view ###

**Description:**

The clinical importance of significant past problems has been raised. This information is sufficiently important to be included in the Summary view.

### Add a column for Range in the Observations view ###

**Description:**

Range is specified as an optional content in the Value column. It is not defined in the heading and the specification does not give a format for how to return range.

### Minor changes to wording ###

**Description:**

Small changes to correct typos or make small non-consequential changes to improve the text. A collection of changes from reviewing the draft copy. 

### Realign requirements for date handling in html implementation guidance ###

**Description:**

The HTML implementation guidance layout page covers the requirements for date filtering and standards for date banners. The content has been added to and is set within the requirements for the layout and descriptions of standard banners. The date filtering is not specifically about the layout.
The flow of the details about the layout and standard banners may be improved by moving the date filtering details outside of the banners section. The clarity of the rules regarding date filters and default dates may be clearer if presented together in its own section with banner content covered separately.

---

## 0.7.0 changes ##

### S-Flag patients to return Patient Not Found in ARHTML ###

**Description:**

- version 0.5.0 of ARHTML HTML implementation standards states that demographic details are to be redacted for patients which are S-flagged on Spine e.g. 'May be redacted if patient is flagged on Spine as Sensitive demographics.' This has been queried and subsequently changed in other capabilities for providers not to return patient records for S-flagged patients but to return a 'Patient Not Found' error.

### Default date range if only a start or end date parameter passed in getCareRecord ###

**Description:**

- the scenario where only a start or an end date need to be considered and the GP Connect program needs to update the specification to cater for the possibility of someone only sending a start date or an end date

### Default Date Range Banner Message Wording ###

**Description:**

- change default date range range banner message wording

### Clarify acceptable usage of sub-section banners and uplift the specification ###

**Description:**

- the layout of sections and subsections has been standardised to avoid supplier variance

### Ensure all HTML Views have a runnable CodePen and a rendered raw HTML version with realistic data ###

**Description:**

- CodePens have been used to provide examples of what the HTML might look like. They have been provided as an aid for developers.

### Medications Prescribed Elsewhere ###

**Description:**

- the inclusion of a Medications Prescribed Elsewhere (MPE) was considered to be out of scope for HTML View 0.5.x specification releases. Further investigation and clinical engagement has indicated that there is a significant need for this information in the HTML View.

### Medication Issues ###

**Description:**

- there is a usability issue within the “Current Medication Issues” section. Specifically the handling of multiple entries for repeat medications (every issue is itemised)
	
	there is also the issue of the repeat medication entries and acute medication entries being bundled together, which makes it difficult for a clinician to review

	feedback from FoT has highlighted that large amounts of data in the Current Medication Issues subsection of the Summary section reduces its effectiveness as a quick overview and risks subsequent subsections being overlooked

### Reason for discontinued and cancelled medication ###

**Description:**

- it is extremely important for the details regarding the ending of a medication to be available to a clinician, as this will highlight any clinical issues (e.g. stopping a medication due to an allergy etc.) and allow the clinician to make an efficient and informed clinical decision.   Specification 0.5.x only requires a cancelled/discontinued and date to be included in the Details column. The reason is not specified as required.   “Where the medication was cancelled (Acute) or Discontinued (Repeat), this should be included in the Details column as Cancelled followed by Date of Cancellation or Discontinued, followed by Date when discontinued.

### Current is not explicitly defined for medication subsection content ###

**Description:**

- it is imperative that the application of rules for the placement and transition of individual medication item entries within the 3 sub sections is clearly understood and any mitigating text is appropriately provided.

	currently this is not the case, therefore a clinician will get differing views depending on the supplier providing the data (and potentially the specific GP Practice where a local configuration setting can determine the age for ‘current’) and there is no text explaining the differences.

### Separate the dosage information from the medications details columns ###

**Description:**

- clinician feedback has highlighted that it would be useful to have a separate dosage column across all of the medications sub sections. The information is currently available within the text about the medication item, making this a usability issue.   The availability of a separate dosage column makes it easier or a clinician to ‘compute’ and make clinical assessments and decisions.

### Add a definition for the application of decimal places for numeric value ###

**Description:**

- First of Type feedback has noted that some values are presented to a number of decimal places which could misrepresent the accuracy of recording or make it less user friendly to read the values, for example, in the Observations section

### Summary page - reordering of sections ###

**Description:**

- First of Type feedback has noted that the first 3 encounters should be the first subsection on the Summary page

### Add section for CSS styling ###

**Description:**

- for an improved consumer experience, details regarding HTML IDs and classes need to be added to the Implementation Standards page

### Remove Provider Variance in 0.7.0 ###

**Description:**

- 0.5.1 introduced a Provider Variance page. This has been removed from 0.7.0 as the requirements have been firmed up regarding the differences between provider supplier systems

### Standards and Layout requirements ###

**Description:**

- the requirements listed in 0.5.1 were downgraded from **MUST** to **SHOULD** to avoid the provider suppliers having to make any code changes

	0.7.0 has introduced firm MUST requirements to minimise provider variance.