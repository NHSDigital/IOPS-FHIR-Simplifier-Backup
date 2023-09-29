## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Introduction to the Access Document capability
</div>

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>TO DO</b>: LINKS NEED ADDING
</div>

### Introduction
The Access Document capability provides the ability to retrieve unstructured documents from a patient’s registered GP practice.

### FHIR® resources
The FHIR resources <b>[LINK TO Retrieve a document]</b> pages provide a detailed reference on population and consumption of the FHIR profiled resources used in this capability.

### API definition
The following API definitions are included in this capability:

- Search for a patient’s documents <b>[LINK TO Search for a patient's documents]</b>
- Retrieve a document <b>[LINK TO Retrieve a document]</b>

### Spine interactions

<table data-responsive>
    <thead>
        <tr>
            <th>Operation</th>
            <th>InteractionID</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Read metadata (Access Document)</span></td>
            <td>urn:nhs:names:services:gpconnect:documents:fhir:rest:read:metadata-1</td>
        </tr>
        <tr>
            <td>Patient search (Access Document)</span></td>
            <td>urn:nhs:names:services:gpconnect:documents:fhir:rest:search:patient-1</td>
        </tr>
        <tr>
            <td>Search for documents</span></td>
            <td>urn:nhs:names:services:gpconnect:documents:fhir:rest:search:documentreference-1</td>
        </tr>
        <tr>
            <td>Retrieve document</span></td>
            <td>urn:nhs:names:services:gpconnect:documents:fhir:rest:read:binary-1</td>
        </tr>
    </tbody>
</table>