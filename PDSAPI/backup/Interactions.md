## Interactions

The PDS FHIR API supports FHIR RESTful interactions to:

# Search for a patient
# Update a patient record
# Search for a related person


## Search for a patient

## Overview

You can search using a combination of:

    - given name
    - family name
    - gender
    - postcode
    - date of birth (range)
    - date of death (range)
    - registered GP practice

Ensure that the search parameters are url encoded, especially when containing special characters.

{{render:SearchPatientDiagram}}

## Search types

This endpoint will search for a patient using one of four search types. The choice of search is automatic and will cascade as necessary until results are found. Searches are case-insensitive.

- #### Simple search
    The fastest match, requires family_name, first_name, gender, birth_date. Returns either a single matching patient or nothing. A limited set of parameters can be provided, all of which must exactly match the current information held.

- #### Advanced search
    Can return multiple matching patients if the information provided matches the current information held. Supports searching against additional information fields. 

    Wildcards ( * ) in name and postcode fields are supported. Wildcards must be preceeded by at least two characters, i.e. 'Br*' is valid, but '*cDougal' is not. Multiple wildcards are allowed, for example 'Br*w*' will match 'Brown' and 'Brower'.

- #### Advanced historic search
    Identical to advanced except it also searches historic patient data, for example previous names or addresses.

- #### Weighted search
    Returns a percentage match weight for each potentially matching patient. Always searches historical data. Requires at least one of the following combinations of search parameters:

    - family_name, first_name, gender, birth_date (or range)
    - family_name, gender, birth_date (or range), postcode
    - first_name, gender, birth_date (or range), postcode


## Update a patient record

Use this endpoint to update patient details in PDS.

This is a 'PATCH' operation, meaning you can update specific parts of the patient record (such as a name or an address), as opposed to having to update the entire record.

{{render:UpdatePatientDiagram}}

### Patient record versioning
To update a patient's record you must have retrieved it first. 
When you retrieve a patient record, you get a version number for the record (in the *ETag* header and in the versionId field in the response). 
You must then pass the record's version number in the update request (in the *If-Match* header). 
The update will only succeed if the patient record has not been updated in our database in the meantime. If the update succeeds, you will receive a copy of the update record in the response, including the new record version number. If you have a subsequent update you must use the new version number.


## Search for a related person

Use this endpoint to get a patient's related people details from PDS for a given NHS Number. This is a list of people who can be contacted, and how, regarding the patient. These details may be useful for a practitioner to get in contact with a next of kin or guardian.

{{render:ReadRelatedPersonDiagram}}

**Parameters**

|parameter|data type|notes|
|--
|id (required) |string|The patient's NHS Number. The primary identifier of a patient, unique within NHS England and Wales. Always 10 digits and must be a valid NHS Number.|


