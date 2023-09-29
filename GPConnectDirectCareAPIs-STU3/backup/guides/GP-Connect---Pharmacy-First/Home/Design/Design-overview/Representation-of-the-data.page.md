## {{page-title}}

ITK3 is being used as the vehicle to transport the data between care settings, as it is well-established across GP and pharmacy system suppliers.

The representation, however, makes use of the GP Connect data model (FHIR STU3 representation) - which is the same model that is used by GP Connect - Access Record: Structured, and GP Connect - Patient Facing Services.

The intention is that the vehicle can be changed (for example, from ITK3 to a REST API) - but the FHIR profiles (outside of those required for ITK3) can still be ingested - rather than having to build new mappers to ingest data from the FHIR representation to the receiving system internal data model.

The initial use cases for this capability are pharmacy-based, and care has been taken to ensure that the fields within the [PRSB Pharmacy Standard (V3.01)](https://prsb2.vercel.app/page/community-pharmacy-standardv3) can be represented, without bespoke requirements on the FHIR representation that deviate from the existing profiles.

Each use case will be indicated via the appropriate SNOMED CT code using the {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}, within the `type` element.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The use cases for this capability can be represented using the same FHIR profiles; however, not all profiles will need to be used. The diagrams below attempt to articulate which profiles may be used for each use case.
</div>


---