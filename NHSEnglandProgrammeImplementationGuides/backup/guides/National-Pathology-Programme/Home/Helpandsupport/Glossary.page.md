---
topic: Glossary
---
## Glossary
A separate glossary of developer related terms used by NHS England specifications can be found on the [NHS Developer Hub](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms).

The following terms are of particular relevance to this implementation guide:

<table class="regular">
    <thead>
        <tr>
            <th width="10%">Abbreviation / Acronym</th>
            <th width="25%">Term</th>
            <th width="55%">Definition</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>EDIFACT</td>
            <td>Electronic Data Interchange For Administration, Commerce and Transport</td>
            <td>An international standard for exchanging information electronically, used as the basis for the <b>PMIP EDIFACT (NHS003)</b> messaging specification.</td>
        </tr>
        <tr>
            <td>FHIR</td>
            <td>Fast Healthcare Interoperability Resources</td>
            <td>A standard for exchanging healthcare information electronically, developed by <b>HL7 International</b>. The first formal release of FHIR (DSTU 1) was published in 2014.</td>
        </tr>
        <tr>
            <td>HCP</td>
            <td>Healthcare Professional</td>
            <td>Any healthcare worker responsible for the care of patients.</td>
        </tr>
        <tr>
            <td>HL7 International</td>
            <td>Health Level 7 International</td>
            <td>An organisation that provides standards relating to the exchange, integration, sharing, and retrieval of electronic healthcare information.</td>
        </tr>
        <tr>
            <td>HL7v2.x</td>
            <td>Health Level 7 v2.x</td>
            <td>A set of standards for exchanging heathcare information electronically, developed by <b>HL7 International</b>. The first formal release of HL7v2 (HL7v2.0) was published in 1988.</td>
        </tr>
        <tr>
            <td>LIMS</td>
            <td>Laboratory Information Management System</td>
            <td>A laboratory information management system (LIMS), sometimes referred to as a laboratory information system (LIS) or laboratory management system (LMS), is a software system that supports a laboratory's clinical and business operations.</td>
        </tr>
        <tr>
            <td>MESH</td>
            <td>Message Exchange for Social Care and Health</td>
            <td>MESH is the main asynchronous messaging service used across health and social care in England. It is used to transfer electronic messages directly from one application to another, so that different organisations can communicate securely. Pathology laboratories currently use MESH to communicate test results to GP practices.</td>
        </tr>
        <tr>
            <td></td>
            <td>Pathology Laboratory</td>
            <td>A laboratory where tests are carried out on clinical specimens to obtain information about the health of a patient to aid the diagnosis, treatment, monitoring and prevention of disease. The terms pathology laboratory and laboratory are used interchangeably throughout this implementation guide.</td>
        </tr>
        <tr>
            <td>PBCL</td>
            <td>Pathology Bounded Code List</td>
            <td>The Pathology Bounded Code List (PBCL) was developed to provide a defined or bounded subset of Read codes for use in laboratory to GP messaging. It is currently used in conjunction with the <b>PMIP EDIFACT (NHS003)</b> messaging specification. A set of semantically equivalent <b>SNOMED PBCL</b> concepts have since been created.</td>
        </tr>
        <tr>
            <td>PMEP</td>
            <td>Pathology Messaging Enabler Programme</td>
            <td>A programme that was established by the NHS to define what became known as the <b>PMIP EDIFACT (NHS003)</b> messaging specification, and set up the required infrastructure to support its use.</td>
        </tr>
        <tr>
            <td>PMIP</td>
            <td>Pathology Messaging Implementation Programme</td>
            <td>A programme that was established by the NHS after <b>PMEP</b> to support the adoption of the <b>PMIP EDIFACT (NHS003)</b> messaging specification.</td>
        </tr>
        <tr>
            <td></td>
            <td>PMIP EDIFACT (NHS003)</td>
            <td>A messaging specification that defines the data structure of pathology test reports that flow between laboratories and GP practices in England. The specification is published as an information standard, <a href="https://webarchive.nationalarchives.gov.uk/ukgwa/20150107154542/http:/www.isb.nhs.uk/documents/isb-1557">ISB 1557 EDIFACT Pathology Messaging Standard (Amd 39/2003 EDIFACT v1.003)</a>.</td>
        </tr>
        <tr>
            <td>SNOMED CT</td>
            <td>Systematized Nomenclature of Medicine Clinical Terms</td>
            <td>The preferred ontology for coding clinical concepts in the UK, also referred to as SCT.</td>
        </tr>
        <tr>
            <td></td>
            <td>SNOMED PaLM</td>
            <td>SNOMED CT concepts representing laboratory test request and test result codes. To aid implementation, the content is published in the following SNOMED CT reference sets:<br><br>
                <ul>
                    <li>1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set - containing laboratory test request codes</li>
                    <li>1853551000000106 | PaLM (Pathology and Laboratory Medicine) observable entity simple reference set - containing more granular, detailed laboratory test result codes than those in the <b>SNOMED PBCL</b> reference set</li>
            </td>
        </tr>
        <tr>
            <td></td>
            <td>SNOMED PBCL</td>
            <td>SNOMED CT concepts representing laboratory test result codes. These are semantically equivalent to <b>PBCL</b> Read codes. To aid implementation, the content is published in the following SNOMED CT reference set:<br><br>
                <ul>
                    <li>999002881000000100 | Pathology Bounded Code List (PBCL) observables simple reference set - containing laboratory test result codes</li>
            </td>
        </tr>
        <tr>
            <td></td>
            <td>Test Group</td>
            <td>Used within this implementation guide to denote a set of related tests that are reported together, for example a Full Blood Count. The individual tests within a test group may differ between organisations. Test groups are more widely referred to as batteries, panels or profiles.</td>
        </tr>
        <tr>
            <td>UTL</td>
            <td>Unified Test List</td>
            <td>SNOMED CT concepts representing laboratory test request and test result codes. The Unified Test List has been superseded by <b>SNOMED PaLM</b>. </td>
        </tr>
    </tbody>
</table>