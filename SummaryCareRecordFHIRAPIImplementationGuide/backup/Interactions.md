## Interactions

This page details the interactions between systems, senders, receivers etc. 
It should contain the interaction information and diagram to illustrate the interactions. 

The SCR API will present a simple single interface for consumption to the supplier system such that the supplier is not aware that interactions are taking place with two spine systems (SCR and ACS). I.e. the SCR API will follow a facade pattern.
The SCR API will be implemented as a FHIR R4 compliant API

In summary:

Consumers will call a proxy at the GCP zone (apigee) where authentication is applied via the brokered NHS ID model. 

Upon successful authentication, the request is passed through to the SCR FHIR API which acts as a facade to three spine APIs

Four spine APIs are used by the SCR FHIR API:

* SCR HL7 V3 POST. This API will accept a GP Summary Upload payload which is expected by the REPC_IN150016UK05 spine TMS interaction. This results in a new "latest" GP Summary document being stored in spine according to the existing SCR process.
* /Polling API (which has been created for the PDS Update API) will be augmented to enable the consumer (the SCR FHIR API in this case) to discover the state of the upload (success, failure, work in progress). Logic underlying this will re-use the mechanism created for PDS Update whereby spine core does not initiate a callback to a supplier TMS endpoint, but rather makes the result available via the polling endpoint.
* ACS is an existing spine web service which is used by SCR to update consent to share their GP record with SCR status for a patient. Work here is limited to making this API available through IGway3, which may be just configuration.

* SCR API offers interactions to retrieve the latest SCR identifier and the latest SCR document, and to set Permission to view:
* {{pagelink:getscrid}}
* {{pagelink:getscrdocument}}
* {{pagelink:setpermission}}

* SCR API offers a Post Alert endpoint and interaction to allow 
GP Systems to create and record Permissioin to view Alerts
* {{pagelink:postalert}}

{{render:architecture-scr}}