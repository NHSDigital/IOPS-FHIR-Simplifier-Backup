## {{page-title}}

The prototype UKCore Reference Server is internally one single server. There are two means of accessing it:

- Unauthenticated access 
- Secure Access

For this Hackathon it is expected only the Unauthenticated access is needed, but the secure access has been added in case of more complex discussions around FHIR interactions are desired.

<i class="fa fa-info-circle"></i> Please note: the reference implementation server uses [paging](https://hl7.org/fhir/R4/http.html#paging), with a page size of 20 results.

---

### Unauthenticated Access 

Unauthenticated access is split into logical sections which are based around potential standards and/or standards used internationally.  

Available on these servers:

| API Documentation |  Frameworks and Implementation Guides | FHIR Server baseUrl |
|--
| [Clinical Data Sharing](http://lb-fhir-facade-926707562.eu-west-2.elb.amazonaws.com/swagger-ui/index.html) RESTful endpoint providing read-only access for care resources. This API can be found on several EPR and other systems. |  [IHE-QEDM](https://www.ihe.net/uploadedFiles/Documents/PCC/IHE_PCC_Suppl_QEDm.pdf) and [HL7 UK - UKCore Access](https://build.fhir.org/ig/HL7-UK/UK-Core-Access/) (in-progress UK equivalent). Both aim at establishing common query API's across the health and social care enterprise.  See also Framework - [Shared Observation Records](https://simplifier.net/guide/UKCore-Hackathon/Home/Frameworks/Observations-and-Diagnostic-Reports?version=current#Shared-Observation-Records) and [Clinical Observations](https://simplifier.net/guide/clinicalobservations/introduction?version=current) <br/><br/> [IHE-MHD Finding and Retrieving Documents](https://profiles.ihe.net/ITI/MHD/index.html), see also Framework [Document Sharing](https://simplifier.net/guide/UKCore-Hackathon/Home/Frameworks/Document-Sharing) | https://3cdzg7kbj4.execute-api.eu-west-2.amazonaws.com/poc/clinicaldatasharing/FHIR/R4  |
| [Orchestration Services](http://lb-hl7-tie-1794188809.eu-west-2.elb.amazonaws.com/swagger-ui/index.html) RESTful queries and interactions across health administration resources and bulk resource transfers  | [IHE-MHD Sending Documents](https://profiles.ihe.net/ITI/MHD/index.html) FHIR version of IHE-XDS api's which can also be used with other EDMS. See also Framework  [Document Sharing](https://simplifier.net/guide/UKCore-Hackathon/Home/Frameworks/Document-Sharing) <br/> <br/> [FHIR Structured Data Capture](http://hl7.org/fhir/uv/sdc) for handling forms, see also Framework - [Questionnaires and Structured Data Capture](https://simplifier.net/guide/UKCore-Hackathon/Home/Frameworks/Questionnaires-and-Structured-Data-Capture?version=current) <br/> <br/> [HL7 FHIR Workflow](http://hl7.org/fhir/R4/workflow-module.html) | https://3cdzg7kbj4.execute-api.eu-west-2.amazonaws.com/poc/events/FHIR/R4 | 
| [Conformance and Validation.](http://lb-fhir-validator-924628614.eu-west-2.elb.amazonaws.com/swagger-ui/index.html)| [HL7 FHIR Validation](http://hl7.org/fhir/R4/validation.html) | https://3cdzg7kbj4.execute-api.eu-west-2.amazonaws.com/poc/Conformance/FHIR/R4 | 


---

### Secure Access

This FHIR Server supports a wider range of FHIR RESTful interactions (see https://cnuc9zdola.execute-api.eu-west-2.amazonaws.com/dev/metadata).
Direct access to this server requires authentication, details are available if required. 


| Service | Url |
|--
| Using Postman | https://github.com/awslabs/fhir-works-on-aws-deployment#using-postman-to-make-api-requests |
| FHIR Server BaseUrl | https://cnuc9zdola.execute-api.eu-west-2.amazonaws.com/dev |
| AWS Cognito TokenUrl | https://1cqk42q02th79tba81omg430ku.auth.eu-west-2.amazoncognito.com/oauth2/token |