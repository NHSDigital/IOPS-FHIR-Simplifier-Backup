## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>



The Directory of Service standard aims to provide a common framework for NHS DoS services to align.

The DoS standard has been modelled around the FHIR resources HealthcareService, Location, Slot and Schedule. 

It is modelled on the FHIR Scheduling workflow that is also present in the  <a href='https://build.fhir.org/ig/IHE/ITI.Scheduling/volume-1.html ' target="_blank">IHE ITI Scheduling documentation</a>

- The Standard provides a <a href='https://hl7.org/fhir/R4/http.html' target="_blank">FHIR RESTful interface</a> within which transactions are performed directly on the server resource using synchronous endpoints using GET, POST and PUT HTTP verbs.

- As a pre-requisite for calling the DoS FHIR R4 Standard , client systems MUST have traced the patient on PDS to ensure they have the correct NHS number for the patient. The <a href='https://developer.nhs.uk/apis/spine-core/pds_overview.html' target="_blank">Spine Core API spec</a> outlines the approaches available for this demographic trace.

- The DoS FHIR R4 Standard will be hosted on the NHS England API Platform. Refer to - {{pagelink:Home/Build/Authentication.page.md}}. 

- The DoS allows systems to interoperate in a FHIR format that conforms to the proposed R4 guidance, and <a href='https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence?version=1.7.0' target="_blank">UK Core</a>

- The DoS uses a variety of FHIR resources that can be found on the {{pagelink:Home/FHIR-Assets/Profiles}} page.

<!-- INCLUDE A RENDER DIAGRAM -->
<!-- {{render:xyz-profile-connections}} -->