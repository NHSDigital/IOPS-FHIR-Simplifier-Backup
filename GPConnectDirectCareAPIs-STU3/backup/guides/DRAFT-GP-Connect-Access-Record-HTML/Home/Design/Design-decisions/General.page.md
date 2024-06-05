## {{page-title}}

### Record ‘In-transit’ as a result of GP transfer
If the patient’s record is indicated in the provider system as not fully-integrated following a GP to GP transfer, then only data which has been entered to the current GP record should be returned, and NOT the contents of the previous GP record. Where data is excluded according to this, a warning should be included in the section banner indicating that some data has been excluded as a result of the transfer.

- <span class="label label-success">SELECTED</span> provider to supply a warning that the record could be incomplete
- other

<span class="label label-info">DECISION</span> The provider MUST display a banner message when a record is in-transit.

### Deceased patient’s record
Behaviour when a deceased patient’s record is requested:

- <span class="label label-info">DECISION</span> The provider MUST allow access to a deceased patient’s record for a period of 28 days after the patient’s death. The provider MUST allow for the period to be configurable. If the request is made after this period, the provider MUST return an error.
- <span class="label label-info">DECISION</span> The provider MUST return a deceased patient’s record only if the patient was a main GMS registered patient prior to being de-registered due to death.

### Record locking
Behaviour when Access Record query/request received while patient record being updated in provider system:

- <span class="label label-success">SELECTED</span> return the requested record section, only including data that has been successfully committed to the database and is available to all users
- return error message in lieu of record section.
- return snapshot of record as-is at the time of request including any non-committed changes

<span class="label label-info">DECISION</span> The provider MUST return the most recently committed record for the patient.

### Requesting a section
How can the HTML sections be requested?

- [0..N] return a variety of views
- [0..1] return everything vs. Return summary
- <span class="label label-success">SELECTED</span> [1] only return a single section at a time

<span class="label label-info">DECISION</span> The ability to return multiple or all HTML care record sections in one request will not be provided.

#### HTML section ordering
How should the HTML sections be ordered?

<span class="label label-info">DECISION</span> Consumer systems MUST provide access to record sections in the order specified, which is captured in the ordering of the HTML composition sections with-in the FHIR `gpconnect-carerecord-composition-1` data model.