## {{page-title}}

Is based on [FHIR Workflow](https://www.hl7.org/fhir/r4/workflow.html) and [FHIR Structured Data Capture Workflow](http://hl7.org/fhir/uv/sdc/workflow.html#form-solicitation) 

### Overview

1. The organisation or practitioner who wishes a form to be completed, will first find the form on a registry called `Form Manager`. See [GET /Questionnaire](http://lb-fhir-validator-924628614.eu-west-2.elb.amazonaws.com/swagger-ui/index.html#/Structured%20Data%20Capture). 
If the forms does not exist see {{pagelink:Home/Technical-Framework/Structured-Data-Capture/1.-Creating-the-Form.page.md}}
2. A request is made to the service, patient or practitioner to complete the form. This is assumed to be via a FHIR Task resource, see [POST /Task](http://lb-hl7-tie-1794188809.eu-west-2.elb.amazonaws.com/swagger-ui/index.html#/FHIR%20Workflow)
3. The form is completed and the results stored on a repository. See {{pagelink:Home/Technical-Framework/Structured-Data-Capture/2.-Completing-the-Form.page.md}}
4. The FHIR Task is updated to be completed, see [PUT /Task](http://lb-hl7-tie-1794188809.eu-west-2.elb.amazonaws.com/swagger-ui/index.html#/FHIR%20Workflow) 

{{render:diagrams-TechnicalFramework-sdc-complete-form-duplicate-2}}