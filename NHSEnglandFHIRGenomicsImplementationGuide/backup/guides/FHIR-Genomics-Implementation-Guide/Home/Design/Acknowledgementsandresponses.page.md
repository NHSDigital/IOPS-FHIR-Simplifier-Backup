## {{page-title}}

It is expected that acknowledgements will conform to the [NHSDigital FHIR Acknowledgement Framework](https://simplifier.net/guide/acknowledgement-framework?version=current). This framework and associated IG are still in development. Once published, a link to the IG, and how to interpret the framework for use in Genomics will be provided here.

Until this is finalised, it is expected that Create requests (POSTs) of resources will result in OperationOutcome resources being returned, with links to retrieve the saved resources, if successful, to ensure data has been appropriately parsed by the service and to notify users of the unique IDs assigned to resources. If unsuccessful, the OperationOutcome will contain diagnostics from the FHIR validation service to guide users on how to correct errors in their request.

Transactions will result in 'transaction-response' bundles being returned. These will contain a set of OperationOutcome resources, each detailing the success or error state of an individual resource. If any one resource fails validation, the whole transaction is failed to ensure resources are not orphaned and maintain referential integrity (as per the [FHIR Transaction Rules](https://hl7.org/fhir/R4/http.html#transaction)). Examples of transaction responses can be found under the {{pagelink:Home/Examples/Bundle}} example pages.

View requests will result in the the resource itself being returned, of requested by ID, or encapsulated within a searchset Bundle if searched for using other parameters.

Update or Delete events will result in OperationOutcome resources being returned, to notify the client of the outcome of the request, detailing either success of failure codes.
