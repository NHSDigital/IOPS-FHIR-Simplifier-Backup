## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> Consider using <i>Store and Notify</i> instead of the <i>Message Broker</i> pattern as this also supports <i>Shared Clinical Document</i> (NRL) pattern</div>

NHS England standards for FHIR Message API's are:

### Events

- [National Event Management System](https://digital.nhs.uk/developer/api-catalogue/national-events-management-service-fhir) (FHIR Message STU3)
- [Transfer of Care](https://digital.nhs.uk/developer/api-catalogue#t) FHIR Message and Document STU3
- [Digital Medicine](https://digital.nhs.uk/developer/api-catalogue/digital-medicine-fhir) FHIR Message and Document STU3 depreceated

### Request

- [Bookings and Referrals (BARS)](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir) (FHIR Message R4)
- [Electronic Prescription Service (EPS)](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir) (HL7 FHIR Message R4)


Will normally follow [FHIR Workflow Ad Hoc Communication - Option A: Simple RESTful POST or PUT](https://hl7.org/fhir/R4/workflow-ad-hoc.html#optiona) using either MESH or an operation ([$process-message](https://hl7.org/fhir/R4/messaging.html#operations))

See also [NHS England Interoperability Handbook - Message Broker](https://www.england.nhs.uk/wp-content/uploads/2017/03/interoperabilty-handbk.pdf)

{{render:diagrams-TechnicalFramework-Workflow-DocumentMessageBroker}} 

Will often focus on either the `request` part of a workflow or the result outcome - the `event`. 
Events are not tied to the Request and will often be generated at key trigger points such as patient admitted or discharged.





