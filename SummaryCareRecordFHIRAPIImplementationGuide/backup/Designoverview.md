## Design overview

The SCR adaptor design will follow the guiding design principle that the adaptor seeks to hide legacy complexity where possible.

The SCR API will fully hide the consumer from all details of the HL7 messaging formats used to convey SCR based information to spine.

The SCR API will fully hide the consumer from knowledge of the spine TMS messaging requirements defined to enable transport of HL7 messaging to spine.

The SCR API will fully hide details of the ACS integration details such as spine SOAP web service implementation details.