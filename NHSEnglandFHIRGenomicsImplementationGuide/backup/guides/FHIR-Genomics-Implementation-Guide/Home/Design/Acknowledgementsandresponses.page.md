## {{page-title}}

It is expected that acknowledgements will conform to the [NHSDigital FHIR Acknowledgement Framework](https://simplifier.net/guide/acknowledgement-framework?version=current). This framework and associated IG are still in development. Once published, a link to the IG, and how to interpret the framework for use in Genomics will be provided here.

Until this is finalised, it is expected that individual Create or Update requests (POSTs and PUTs) that are successful will result in the created resources being returned, along with the server assigned IDs to ensure the source system can retrieve the resources at a later time. Create or Update requests bundled together into Transaction Bundles, or operations which encounter validation errors will result in OperationOutcome resources being returned, with links to retrieve the saved resources, if successful, to ensure data has been appropriately parsed by the service and to notify users of the unique IDs assigned to resources. If unsuccessful, the OperationOutcome will contain diagnostics from the FHIR validation service to guide users on how to correct errors in their request.

Transactions will result in 'transaction-response' bundles being returned. These will contain a set of OperationOutcome resources, each detailing the success or error state of an individual resource. If any one resource fails validation, the whole transaction is failed to ensure resources are not orphaned and maintain referential integrity (as per the [FHIR Transaction Rules](https://hl7.org/fhir/R4/http.html#transaction)). Examples of transaction responses can be found under the {{pagelink:Home/Examples/Bundle}} example pages.

View requests will result in the the resource itself being returned, of requested by ID, or encapsulated within a searchset Bundle if searched for using other parameters.

Note, if Delete events are supported, these will result in OperationOutcome resources being returned, to notify the client of the outcome of the request, detailing either success of failure codes. Support for Delete operations is still under discussion as of the time of publication.
