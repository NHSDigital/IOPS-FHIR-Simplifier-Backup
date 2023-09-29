### Responses

Where the outcome of a search does not result in a Bundle or a resource, you can use the [OperationOutcome](http://hl7.org/fhir/operationoutcome.html) resource. 

 The OperationOutcome resource is used in the following circumstances:

- When a RESTful interaction or operation fails
- As the response on a validation operation to provide information about the outcome
- As part of a message response, usually when the message has not been processed correctly
- As the response to a batch/transaction, when requested
- As part of a search's Bundle response containing information about the search


### Outcomes

The values to be populated for the OperationOutcome resource are as follows:

`OperationOutcome.issue.details.code` - Value from the **Code** column below.

`OperationOutcome.issue.details.display` - Detailed description about the error.


#### General

|Code 	|Response Code |	Description|
|--
|ACCESS_DENIED 	|401 	|Used when the user does not have permission for a particular request. eg. when their asid does not have the correct interactions attached to it.|
|FAILURE_TO_PROCESS_MESSAGE |	500 	|A default message when something really bad has happened that the system could not handle.|
|UNABLE_TO_CALL_SERVICE |	408 	|For a synchronous request, the downstream domain processing has not completed within the configured timeout period.|
|UNSUPPORTED_SERVICE |	400 	|The service the user requested an endpoint that does not exist - so is unsupported. eg. /Patient/9999999999/Pets|
|RESOURCE_NOT_FOUND |	404 	|The resource was not found.|
|INVALID_RESOURCE_ID| 	400 	|The resource id was not valid. For example a NHS Number is presented which is not a valid NHS Number.|
|INVALIDATED_RESOURCE |	404 	|The resource has been invalidated so could not be returned.|

#### Search

|Code 	|Response Code |	Description|
|--
|INVALID_SEARCH_DATA |	400 	|The search parameters are invalid. A description of what exactly is at fault will be added to the display.|
|TOO_MANY_MATCHES |	200 |	Too many matches were found - user should be told to refine their search parameters.|

#### Update

|Code |	Response Code |	Description|
|--
|PRECONDITION_FAILED 	|412 	|Request missing basic requirements such as If-Match header (or invalid headers).|
|RESOURCE_VERSION_MISMATCH 	|409 	|The resource version has changed since your last read, so the update has been rejected.|
|FORBIDDEN_UPDATE |	403 |	The user is not permitted to update certain resources or elements - a detailed description will be added to the display. For example - updating a sensitive patient or adding a formal death notification is only permitted from certain systems.|
|VALIDATION_ERROR |	400 |	This it the "default" error thrown when no others are applicable.|
|INVALID_UPDATE |	400 |	The update was invalid - a detailed description will be added to the display.|
|MISSING_VALUE 	|400 |	There was a missing value in the request. For example - a name update that is missing the surname. The missing value will be presented in the display.|
|INVALID_VALUE 	|400 	|There was an invalid value in the request. For example - a name update where the surname is too long. The invalid value and field will be presented in the display.|
|UNSUPPORTED_VALUE 	|400 	|There was an unsupported value in the request. The value may be valid in the schmema - however it could be a legacy value that we do not allow to be set anymore. For example - setting the death notification status to 'removed'. The invalid value and field will be presented in the display.|
|TOO_FEW_VALUES_SUBMITTED 	|400 	|The field in question has a minimum number of items and the user sent too few.|
|TOO_MANY_VALUES_SUBMITTED 	|400 	|The field in question has a maximum number of items and the user sent too many.|
|ADDITIONAL_PROPERTIES 	|400 	|The user sent additional properties within the dictionary. For example sending a patient patch and attempting to add 'pets', which is not an allowed field within the patient resource.|


#### Polling

|Code 	|Response Code 	|Description|
|--
|POLLING_ID_NOT_FOUND 	|404 	|When polling the id was not found - or it was not applicable such as a non polling id.|
|POLLING_MESSAGE_FAILURE 	|422 |	When polling an id, a message was found to be in a failed state, so there is nothing else to be done and should be considered a failure.|