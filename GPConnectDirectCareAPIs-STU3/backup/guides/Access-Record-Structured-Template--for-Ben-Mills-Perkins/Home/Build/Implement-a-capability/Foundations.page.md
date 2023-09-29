## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: All about the common foundation capabilities
</div>

### Purpose

The Foundations capability covers the basic API requirements and prerequisites needed to use the GP Connect APIs.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: To use the GP Connect APIs, you need a level of pre-existing accredited Spine connectivity along with some FHIR foundation API capabilities.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Roadmap</b>: The necessity to have access to pre-existing Spine services (for example, Personal Demographics Service (PDS) and Spine Directory Service (SDS) integration) is likely to be replaced by GP Connect/FHIR based equivalents.
</div>

### Prerequisites

### PDS

You need to be able to provide a verified NHS number to use an API. You can do this using a Spine accredited system, a Demographics Batch Service (DBS) batch-traced record (CSV), or using a Spine Mini Services Provider (HL7v3).

</br>

### SDS / ODS

To resolve a given GP Practice organisation to its URI you need to be able to do a Spine SDS query (LDAP) using the practice's ODS code to perform an SDS End Point Lookup 
({{pagelink:Home/Authentication/Spine-Directory-Services/Overview-and-querying.page.md}}).

#### FHIR

In order to be a compliant FHIR server, provider systems need to expose a valid FHIR [CapabilityStatement](https://www.hl7.org/fhir/STU3/capabilitystatement.html) profile.

Refer to Development Guidance - FHIR API Guidance - Common API Guidance 
({{pagelink:Home/Build/FHIR-development/FHIR--implementation.page.md}}) for full details on the common FHIR API patterns used throughout all the GP Connect APIs.

</br>

## Scenarios ##

- Search for a patient by `NHS Number`
- Search for an organisation by `ODS Code`
- Search for a practitioner by `SDS UserID`

</br>

## API definition ##

The following individual API calls make up the Foundations capability and support the other capability packs:

- [Get the FHIR capability statement](foundations_use_case_get_the_fhir_capability_statement.html)
- [Find a patient](foundations_use_case_find_a_patient.html)
- [Find a practitioner](foundations_use_case_find_a_practitioner.html)
- [Find an organisation](foundations_use_case_find_an_organisation.html)

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>TO DO</b>: links need updating
</div>

</br>

## Spine interactions

The Foundations capability message set includes the following set of Spine interactions:

| Operation                 | InteractionID             | 
|---------------------------|---------------------------| 
| Read Metadata | `urn:nhs:names:services:gpconnect:fhir:rest:read:metadata-1` |
| Read Patient | `urn:nhs:names:services:gpconnect:fhir:rest:read:patient-1` |
| Patient Search | `urn:nhs:names:services:gpconnect:fhir:rest:search:patient-1` |
| Read Practitioner | `urn:nhs:names:services:gpconnect:fhir:rest:read:practitioner-1` |
| Practitioner Search | `urn:nhs:names:services:gpconnect:fhir:rest:search:practitioner-1` |
| Read Organisation | `urn:nhs:names:services:gpconnect:fhir:rest:read:organization-1` |
| Organisation Search | `urn:nhs:names:services:gpconnect:fhir:rest:search:organization-1` |
| Read Location | `urn:nhs:names:services:gpconnect:fhir:rest:read:location-1` | 
| Register Patient | `urn:nhs:names:services:gpconnect:fhir:operation:gpc.registerpatient-1`

</br>

### Implementation and testing

Below is the suggested order in which the Foundations capabilities should be implemented by provider suppliers. The specified order has been recommended around the functionality of the GP Connect Automated Test Suite and any internal dependencies between the test scenarios for the different foundation endpoints.

It is advisable to develop against the Automated Test Suite as this will assist with creating a GP Connect compliant product. By implementing the endpoints in the order below, this means that the automated test suite set of tests for that endpoint can be run during development without the developer seeing errors due to pre-test API calls or post-test validation API calls relevant to the test being run and failing as they have not been developed yet.

</br>

#### Foundation endpoints

<table data-responsive>
    <thead>
        <tr>
            <th>Order</th>
            <th>API Endpoint</th>
            <th>Test Suite Endpoint Dependencies</th>
            <th>Reason For Dependency</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>#1</td>
            <td>Find an organization</td>
            <td>- </td>
            <td>The find an organization capability is not dependent on any other capability within the automated test suite.</td>
        </tr>
        <tr>
            <td>#2</td>
            <td>Read an Organization</td>
            <td>Find an organization</td>
            <td>'Find an organization' is a dependency for 'Read an organization' as it is used to lookup the local identifier from the organization code which is setup in the test suite organization mapping csv file.</td>
        </tr>
        <tr>
            <td>#3</td>
            <td>Find a practitioner</td>
            <td>Read an Organization</td>
            <td>The 'Read an organization' endpoint is required to validate the “managingOrganization” reference returned within the practitioner resource.</td>
        </tr>
        <tr>
            <td>#4</td>
            <td>Read a practitioner</td>
            <td>Find a practitioner / Read an organization</td>
            <td>'Find a practitioner' is required to lookup the logical identifier, from the practitioner user id setup in the test suite practitioner mapping csv file, to use for the read. The 'Read an organization' endpoint is required to validate the “managingOrganization” reference returned within the practitioner resource.</td>
        </tr>
        <tr>
            <td>#5</td>
            <td>Find a patient</td>
            <td>Read and organization / Read a practitioner</td>
            <td>The 'Read an organization' endpoint is required to validate the “managingOrganization” reference returned within the practitioner resource. The 'Read a practitioner' endpoint is required to validate the “careProvider” reference if returned within the patient resource.</td>
        </tr>
        <tr>
            <td>#6</td>
            <td>Read a patient</td>
            <td>Find a patient / Read an organization / Read a practitioner</td>
            <td>'Find a patient' is required to lookup logical identifier from the patient from the NHS number set up in the test suite nhsNoMap csv file. The 'Read an organization' endpoint is required to validate the “managingOrganization” reference returned within the patient resource. The 'Read a practitioner' endpoint is required to validate the “careProvider” reference if returned within the patient resource.
</td>
        </tr>
        <tr>
            <td>#7</td>
            <td>Read a location</td>
            <td>Read an organization</td>
            <td>The 'Read an organization' endpoint is required to validate the “managingOrganization” reference returned within the location resource.</td>
        </tr>
        <tr>
            <td>#8</td>
            <td>Register a patient</td>
            <td>Find a patient / Read a patient / Read an organization</td>
            <td>The register patient endpoint tests require a number of the foundation search and read endpoints to be implemented and therefore it is advised that this is done as the last foundation capability. The foundation endpoints are used to create rich register patient requests as well as validating the registered patient resource is valid and retrievable on the providers system.</td>
        </tr>
    </tbody>
</table>

---