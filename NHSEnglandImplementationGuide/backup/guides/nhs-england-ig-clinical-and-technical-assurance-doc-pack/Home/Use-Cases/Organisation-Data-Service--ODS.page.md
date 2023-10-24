# {{page-title}}

## User stories

- [Data Manager](#data-manager)
- [Clinical Systems Developer](#clinical-systems-developer)
- [Commissioner](#commissioner)
- [Head Clinician](#head-clinician)
- [Consumer](#consumer)

<h2 id="data-manager">Data Manager</h2>

**As a Data Manager:**

- I need access to a single source of data, so that I can assure that the information sourced is correct.
- I need to bring data together from different sources, so that I get meaningful insights to improve patient care and drive change.
- I need help deciding if the API is right for me, so that I get resources or use alternative methods.
- I need to understand at a glance what fields are called, so that I can save time and confusion.
- I need data on a regular basis (at least monthly), so that I can create reports that are up to date.
- I need clearer definitions of roles and relationships so that my reports can track which organisations are operated, commissioned, directed etc and understand impacts of mergers.

### Use Case Flows

### Actors

- Data Managers
- Data Analysts

### Frequency of Use

- Daily, Weekly, Monthly

### Triggers

- Reporting requirements

### Pre-conditions

- Access to clear documentation on how to access and call the API.
- Accurate and contemporaneous data available.
- The Data Consumer's system is functional and has required space and mechanisms available for data import.

### Post-conditions

- Database is populated with data from ODS.
- Reports created and run.
- Data integrated into data visualisation tools such as Power BI.

### Main Course

1. Send a request to ODS API for required data.
1. ODS API processes the request and initiates the data transfer.
1. Receive and store data in database.
1. Parse and validate the data.
1. If any data mismatches or errors are found, they will be logged for further review and action.

### Alternative Course

1. If the initial data request is denied or doesn't go through due to issues like network problems or system failure, there must be a mechanism set in place to retry the request after a specific timeframe.  
1. Data can be manually updated in the directory to match what is published in the ODS database if needed.

### Exception
- If the ODS API is not accessible or new data is not available, the issue should be logged and attempt to connect again after a specific interval.

<hr>

<h2 id="clinical-systems-developer">Clinical Systems Developer</h2>

**Clinical Systems Developer:**

- I need a persistent organisation code identifier, so that I can be confident in the data I integrate to downstream systems.
- I need a FHIR API, so that I can more easily integrate the data with other NHS systems.
- I need to have access to good technical documentation, so that I can assess if the API is applicable for us and how it works.
- I need clearer signposting to clearer information, so that I can save time.
- I need easy access to relationship data, so that I can be confident that commissioning outcomes are correct.
- I need to query intersections of organisation and geographical boundaries so that I can query for all the GP Practices in a statistical geography e.g., local authority.

### Use Case Flows

### Actors

- Clinical Systems Developer

### Frequency of Use

- Daily, Weekly, Monthly

### Triggers

- Integration with downstream systems.

### Pre-conditions

<hr>

## FHIR Assets for Sprint 1

<br>

{{render:Profiles-and-Extensions-All-Extensions-Extension-England-OrganisationRole}}


{{render:Home-Terminology-All-CodeSystems-CodeSystem-England-ODSOrganisationRole}}


{{render:Guide-Home-Terminology-All-ValueSets-ValueSet-England-OrganisationRole}}
