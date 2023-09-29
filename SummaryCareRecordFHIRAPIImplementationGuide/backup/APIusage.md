## API usage

This page is used to describe how the API is used.

The API will be used by GP foundation systems to push information to the central SCR repository upon patient clinical events. These events are essentially where certain data elements the patient's care record at the practice are changed.

The SCR API MVP will expose two API Methods:

Send GP Summary Upload
Update ACS consent status for SCR

1. Send GP Summary Upload
Each time a new GP summary is uploaded to spine, a new immutable clinical document is stored in spine clinicals. This is stored as an HL7 V3 composition. It is this HL7 V3 composition which is later retrieved for viewing by applications such as the Summary Care Record Application

This API method will be implemented as a FHIR R4 UK Core profile of the Composition resource.

2. Update ACS consent status for SCR
Spine clinicals holds the consent status associated with a patient. This is updated via a call to the ACS (Access Control Service) web service API. This status flag indicates two things:

Consent to share core SCR information (defaults to implied consent)
Consent to share Additional Information (this has been changed to implied consent for the purposes of Covid-19 response, though this new consent model may persist)

MIM Links
https://data.developer.nhs.uk/dms/mim/4.2.00/Domains/GP%20Summary/Document%20files/GP%20Summary%20IM.htm

TMS interactions in play are:
REPC_IN150016UK05
MCCI_IN010000UK13
