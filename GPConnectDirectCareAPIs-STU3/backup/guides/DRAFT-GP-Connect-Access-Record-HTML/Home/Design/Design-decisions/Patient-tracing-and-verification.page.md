## {{page-title}}

### GP organisation location
How will the patient’s usual GP practice be identified?

- <span class="label label-success">SELECTED</span> NHS Number MUST BE be used to resolve the ODS code for the patient’s usual GP
- other mechanism

<span class="label label-info">DECISION</span> The patient’s NHS Number MUST BE used to identify their associated ODS code.

### Patient trace handling
Is the consumer or provider responsible for running a trace?

- <span class="label label-success">SELECTED</span> ideally the consumer and provider to have traced in both
- consumer only
- provider only

<span class="label label-info">DECISION</span> Consumers MUST perform a trace.

#### Timeliness of trace for consumers
How often should the trace be run by consumers?

- immediately prior to all API calls
- once per user session
- once per multiple user sessions (meaning, monthly etc.)
- <span class="label label-success">SELECTED</span> within the last 24 hours
<span class="label label-info">DECISION</span> The trace MUST have be performed within the last 24 hours.

### Patient identity cross check
Although a traced national identifier is initially mandated for use with the GP Connect APIs, there are edge case scenarios where the patient record being retrieved from the GP system may have different patient details than the source system. The basic patient resource has been bundled into the response so that a cross check may be performed in the consuming system.

- <span class="label label-success">SELECTED</span> consumer system to cross-check
- provider system to cross-check
- Spine Security Proxy (SSP) to cross-check

<span class="label label-info">DECISION</span> Consumer MUST cross-check with demographics returned from the provider system.

#### Minimum patient demographics
What are the minimum patient demographics that must be returned?

- <span class="label label-success">SELECTED</span> patient banner as defined in the CUI guidance
- community driven (that is, just add Gender)
- absolute minimum (Name, DOB and NHS Number)

<span class="label label-info">DECISION</span> As per GPSoC requirements make minimal registration details mandatory (meaning, First Name, Surname, Gender, DOB) in the FHIR profile.