## {{page-title}}

NHS England standards for FHIR Message API's are:

### Events

- [National Event Management System](https://digital.nhs.uk/developer/api-catalogue/national-events-management-service-fhir) (FHIR Message STU3)
- [Transfer of Care](https://digital.nhs.uk/developer/api-catalogue#t) FHIR Message and Document STU3
- [Digital Medicine](https://digital.nhs.uk/developer/api-catalogue/digital-medicine-fhir) FHIR Message and Document STU3 depreceated

### Request

- [Bookings and Referrals (BARS)](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) (FHIR Message R4)
- [Electronic Prescription Service (EPS)](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir) (HL7 FHIR Message R4)


Are not considered Documents but will often be used as Documents.

#### Request FHIR Messages

Request FHIR Messages will often contain similar data to FHIR Documents without the html representation. However, the recommended content is much less resulting in smaller exchanges of patient record information. FHIR Messages can be said to concentrate more on the transfer of pertinent or key information. 
Request Messages focus on the workflow request, this may be present on a FHIR Document but here this workflow request is implied.

{{render:diagrams-Interactions-FHIR-Message-Request}}


#### Event FHIR Messages

The Event FHIR Messages gist's in the diagram below are based on conversions of HL7 v2 messages to FHIR (these are not NHS England FHIR Message standards). 

{{render:diagrams-Interactions-FHIR-Message-Event}}

Like Request FHIR Messages they only exchange structured data with no html representation.

