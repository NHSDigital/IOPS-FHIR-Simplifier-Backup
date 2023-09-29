<div class="post-header">
   <h1 class="post-title-main">Data model principles</h1>
</div>


  <div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Summary</b>: High-level design principles related to the FHIR&reg; profiles
    </div>
   

   

    

<h2 id="introduction">Introduction</h2>

GP Connect versions 1.x use the
[FHIR STU3](http://hl7.org/fhir/STU3/) standard to specify the API and data models (known as profiles).

<h2 id="interopen">INTEROPen</h2>

<p>GP Connect FHIR profiles specified within this site have been developed by NHS Digital and where available use CareConnect profiles created in collaboration with the INTEROPen community.</p>

<blockquote>
  <p>The INTEROPen vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within England’s health and social care systems.</p>

Find out more on the [INTEROPen website](https://www.interopen.org/)
</blockquote>

<h2 id="profiling-principles">Profiling principles</h2>

<p>When creating the profiled FHIR resources GP Connect have aimed to improve interoperability by:</p>


- aligning, where available, to the CareConnect profiles produced by INTEOPen
- storing profiles on [GitHub](https://github.com/nhsconnect/gpconnect-fhir)</li>
- publishing profiles to [fhir.nhs.uk](https://fhir.nhs.uk)
- carrying the major version in the name of a profile (for example, gpconnect-patient-1) and major/minor version within StructureDefinition/Conformance.
- not mandating profile elements unless this cardinality will apply for all existing and future use cases
- applying must support flags to elements which hold key information within the resources


<h2 id="gp-connect-fhir-profiles">GP Connect FHIR profiles</h2>


> Please see the [FHIR resource guidance page](development_fhir_resource_guidance.html) for further information.
