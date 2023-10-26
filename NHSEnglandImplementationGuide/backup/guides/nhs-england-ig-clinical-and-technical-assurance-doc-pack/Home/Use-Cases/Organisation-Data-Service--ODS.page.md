# {{page-title}}

## User stories

- [Data Manager](#data-manager)
- [Clinical Systems Developer](#clinical-systems-developer)
- [Commissioner](#commissioner)
- [Head Clinician](#head-clinician)
- [Data Consumer](#data-consumer)
- [National Payments System](#national-payments-system)

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

**As a Clinical Systems Developer:**

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

- The ODS API is stable and populated with correct data.
- Information on the data model and schemas is available.
- Good technical documentation is available.

### Post-conditions

- Data is sent to downstream systems.
- Data integrity checks.

### Main Course

1. Write code for making scheduled calls to the API.
1. Write code to integrate ODS data with downstream systems.

### Alternative Course

1. If the initial data request is denied or doesn't go through due to issues like network problems or system failure, there must be a mechanism set in place to retry the request after a specific timeframe.  
1. Data can be manually updated in the directory to match what is published in the ODS database if needed.

### Exception
- If the ODS API is not accessible or new data is not available, the issue should be logged and attempt to connect again after a specific interval.

<hr>

<h2 id="commissioner">Commissioner</h2>

**As a Clinical Commissioner:**

- I need access to a single source of data, so that I can have complete confidence that the data is consistent and contemporaneous.
- I need to know where the data comes from and when it was last changed, so that I no longer have to call to check or do extra work to verify data (last change data).
- I need to be able to take data from one system and use it in another easily, so that I can save time cleaning and reformatting the data.
- I need to have an easy 'look up' tool for codes – or to be able to tell at a glance what a code is for, so that I can check organisation codes don't already exist if I think I need a new one.
- I need clear information on how to use the API, so that I can use it effectively.

### Use Case Flows

### Actors

- Commissioners

### Frequency of Use

- Daily, Weekly, Monthly

### Triggers

- Payment requirements.

### Pre-conditions

- The payment system directory is updated with the new data from ODS.
- Payments are calculated and sent for processing.
- The system is ready for the next update from the ODS API

### Post-conditions

- The payment system directory is updated with the new data from ODS.
- Payments are calculated and sent for processing.
- The system is ready for the next update from the ODS API.


### Main Course

1. Payment System sends a request to ODS API to check for new/amended data.
1. If new data is available, Payment System sends a request to import the new data.
1. ODS API processes the request and initiates the data transfer.
1. Payment System receives and stores the new data.
1. Payment System will then parse and validate the new data.
1. If any data mismatches or errors are found, they will be logged for further review and action.

### Alternative Course

1. If the initial data request is denied or doesn't go through due to issues like network problems or system failure, there must be a mechanism set in place to retry the request after a specific timeframe.  
1. Data can be manually updated in the directory to match what is published in the ODS database if needed.

### Exception
- If the ODS API is not accessible or new data is not available, the issue should be logged and attempt to connect again after a specific interval.

<hr>

<h2 id="head-clinician">Head Clinician</h2>

**As a Head Clinician:**

- I need a persistent identifier, or unambiguous data, so that I can keep track of how well services are performing.
- I need to match ODS codes to people, so that I can say ‘Dr X’ works at this practice – trends and patterns linked to Clinicians.
- I need to compare geographic data, so that I can look into variations of patient care and reduce 'postcode lottery', compare Practices and Trusts.
- I need to be able to spot patterns and trends in aggregated data, so that we can accelerate improvements to patient care.
- I need to be able to visualise data, so that I can more quickly spot trends or anomalies.

### Use Case Flows

### Actors

- Technically skilled clinicians

### Frequency of Use

- Daily

### Triggers

- Data for research and forecasting.

### Pre-conditions

- The ODS API is stable and populated with correct data.
- Information on the data model and schemas is available.
- Relationship, location, and organisation data is readily available.
- Data is in interoperable formats.
- Good technical documentation is available.

### Post-conditions

- Systems are updated with ODS data.
- Systems data can integrate with upstream systems for research, forecasting and modelling purposes.

### Main Course

1. Request sent to ODS API(s) for data.
1. ODS API should authenticate the user.
1. ODS API acknowledges and processes the request and initiates the data transfer.
1. ODS data is received and integrated with our systems.

### Alternative Course

1. If the initial data request is denied or doesn't go through due to issues like network problems or system failure, there must be a mechanism set in place to retry the request after a specific timeframe.  
1. Data can be manually updated in the directory to match what is published in the ODS database if needed.

### Exception
- If the ODS API is not accessible or new data is not available, the issue should be logged and attempt to connect again after a specific interval.

<hr>

<h2 id="data-consumer">Data Consumer</h2>

**As a Data Consumer:**

- I need access to a single source of data, so that I can ensure that the information sourced is correct..
- I need to query for recent changes so I can update my directory in an efficient manner without needing to sync the whole unchanged dataset.
- I need help deciding if the API is right for me, so that I get resources or use alternative methods.
- I need to understand at a glance what fields are called, so that I can save time and confusion when importing the data into the directory.
- I need data on a regular basis (at least daily), so that the directory is always up to date.
- I need clearer definitions of roles and relationships so that my directory can create a hierarchy of parent/child relationships between organisations.

### Use Case Flows

### Actors

- Data Consumer

### Frequency of Use

- Daily

### Triggers

- Data source updates.

### Pre-conditions

- The Data Consumer has the necessary clearance and permissions to access the ODS API.
- The ODS API must be accessible to the Data Consumer.
- The ODS API should have the required and up-to-date data available.
- The Data Consumer's system is functional and has the required space and mechanisms available for data import.

### Post-conditions

- The Data Consumer's directory is updated with the new data from ODS.
- In case of any data mismatches or errors during the import process, they should be logged and corrective actions need to be taken.
- The system is ready for the next update from the ODS API.

### Main Course

1. Data Consumer sends a request to ODS API to check for new data.
1. ODS API authenticates and authorizes the Data Consumer.
1. ODS API sends a response indicating whether there's new data available.
1. If new data is available, Data Consumer sends a request to import the new data.
1. ODS API processes the request and initiates the data transfer.
1. Data Consumer receives and stores the new data in the directory.
1. Data Consumer will then parse and validate the new data.
1. If any data mismatches or errors are found, they will be logged for further review and action.

### Alternative Course

1. If the initial data request from the Data Consumer is denied or doesn't go through due to issues like network problems or system failure, the data consumer must have a mechanism set in place to retry the request after a specific timeframe.  
1. Data can be manually updated in the directory to match what is published in the ODS database if needed.

### Exception
- If the ODS API is not accessible or new data is not available, the Data Consumer should log the issue and attempt to connect again after a specific interval.

<hr>

<h2 id="national-payments-system">National Payments System</h2>

**As a  National Payments System:**

- I need to obtain an accurate list of PCNs (Primary Care Networks) so that I can instigate payment processes for those entities
- I need to identify which GP practices are partner to which PCN with associated dates, so that I can use the data to calculate the level of payment due to each PCN
- I need to obtain confirmation of who the commissioner is for the PCN, so that I can ensure payments are made from the correct budget
- I need to be able to identify who the nominated payee is for the PCN, so that payments can be made to the correct bank accounts
- I need PCN relationship data to be reliable and timely, so that payments are made correctly

### Use Case Flows

### Actors

- Technical/Solutions Architects and System Developers

### Frequency of Use

- Daily

### Triggers

- Payment requirements.

### Pre-conditions

- The ODS API must be accessible to the Payment System
- The ODS API should have the required and up-to-date data available
- The payment system is functional and has required space and mechanisms available for data import
- Every PCN has an ODS code and associated reference data


### Post-conditions

- The payment system directory is updated with the new data from ODS
- In case of any data mismatches or errors during the import process, they should be logged and corrective actions need to be taken
- PCN payments calculated and sent for processing
- The system is ready for the next update from the ODS API

### Main Course

1. Payment System sends a request to ODS API to check for new/amended data
1. ODS API sends a response indicating whether there's new data available
1. If new data is available, Payment System sends a request to import the new data
1. ODS API processes the request and initiates the data transfer
1. Payment System receives and stores the new data in the directory
1. Payment System will then parse and validate the new data
1. If any data mismatches or errors are found, they will be logged for further review and action


### Alternative Course

1. If the initial data request from the Payment System is denied or doesn't go through due to issues like network problems or system failure, the Payment System must have a mechanism set in place to retry the request after a specific timeframe
1. Data can be manually updated in the directory to match what is published in the ODS database if needed


### Exception
- If the ODS API is not accessible or new data is not available, the Payment System should log the issue and attempt to connect again after a specific interval
<hr>

## FHIR Assets for Sprint 1

<div>
{{render:Profiles-and-Extensions-All-Extensions-Extension-England-OrganisationRole}}
</div>

<div>
{{render:Home-Terminology-All-CodeSystems-CodeSystem-England-ODSOrganisationRole}}
</div>

<div>
{{render:Guide-Home-Terminology-All-ValueSets-ValueSet-England-OrganisationRole}}
</div>

<div>
{{render:Home-Profiles-and-Extensions-All-Extensions-Extension-England-DateTime}}
</div>

<div>
{{render:Home-Terminology-All-CodeSystems-CodeSystem-England-ORDDateTime}}
</div>

<div>
{{render:Home-Terminology-All-ValueSets-ValueSet-England-TypedDateTime}}
</div>