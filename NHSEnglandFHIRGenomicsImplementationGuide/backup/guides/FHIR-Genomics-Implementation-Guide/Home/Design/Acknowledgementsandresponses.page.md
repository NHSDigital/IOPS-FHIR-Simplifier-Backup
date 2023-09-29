## {{page-title}}

It is expected that acknowledgements will conform to the [NHSDigital FHIR Acknowledgement Framework](https://simplifier.net/guide/acknowledgement-framework?version=current). This framework and associated IG are still in development. Once published, a link to the IG, and how to interpret the framework for use in Genomics will be provided here.

Until this is finalised, it is expected that Create requests (POSTs) of resources will result in the saved resources being returned to ensure data has been appropriately parsed by the service and to notify users of unique IDs assigned to resources.

View requests will result in the the resource itself being returned, of requested by ID, or encapsulated within a searchset Bundle if searched for using other parameters.

Update or Delete events will result in OperationOutcome resources being returned, to notify the client of the outcome of the request, detailing either success of failure codes.
