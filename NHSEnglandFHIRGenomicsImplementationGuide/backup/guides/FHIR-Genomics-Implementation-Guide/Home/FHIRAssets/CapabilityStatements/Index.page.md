## {{page-title}}

The CapabilityStatements created specifically for use in Genomics are listed below. These include Requirements, defining the profiles to be targeted during validation, and CapabilityStatements defining the endpoints for the Genomic Medicine Service (currently in development). 

The API interactions that make up the service are a combination of FHIR transactions which allow multiple resources to be created and updated at once, and instance level interactions to retrieve or update specific FHIR resources.

The central Test Order Service will expose all API endpoints to enable organisations to create and query test requests, tasks and linked FHIR Resources.

In the linked tables below the API interactions which can be used to create, update and search for information on the test ordering services are specified at a high level.

**Note:** The “Create ServiceRequest”, “Create Task” and “Create Specimen” are all FHIR resource level interactions and could all be performed within one transaction to reduce
the number of API calls required, for example if a GLH creates a new specimen, which they are going to send to an LGL, they should POST the new Specimen, Task and all related resources in one request.

It is expected that the CapabilityStatements will be retrievable from the central Genomic Order Management broker through the `/metadata` endpoint

<!--
@```
from
	CapabilityStatement
select
	name, kind, url
order by
  name
```
-->
{{index:current}}