---
topic: Glossary
---
## Glossary
A general glossary of developer related terms used by NHS England specifications can be found on the [NHS Developer Hub](https://digital.nhs.uk/developer/guides-and-documentation/glossary-of-developer-terms). The following terms are of particular relevance to this implementation guide:

<table class="regular">
    <thead>
        <tr>
            <th width="10%">Abbreviation</th>
            <th width="20%">Term</th>
            <th width="70%">Definition</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>EDIFACT</td>
            <td>Electronic Data Interchange For Administration, Commerce and Transport</td>
            <td>An international standard for electronic data interchange, used as the basis of the <b>PMIP EDIFACT (NHS003)</b> messaging specification.</td>
        </tr>
        <tr>
            <td>HCP</td>
            <td>Healthcare Professional</td>
            <td>Any healthcare worker responsible for the care of patients.</td>
        </tr>
        <tr>
            <td>HL7</td>
            <td>Health Level 7</td>
            <td>HL7 refers to a set of international standards that are used for the transfer of clinical and administrative data between software systems used by healthcare providers. These standards focus on the application layer, which is layer 7 in the OSI model.</td>
        </tr>
        <tr>
            <td>HL7v2.x</td>
            <td>Health Level 7 v2.x</td>
            <td>A set of related HL7 standards for electronic data exchange in healthcare environments, including pathology.</td>
        </tr>
        <tr>
            <td>LIMS</td>
            <td>Laboratory Information Management System</td>
            <td>A laboratory information management system (LIMS), sometimes referred to as a laboratory information system (LIS) or laboratory management system (LMS), is a software system that supports a laboratory's clinical and business operations.</td>
        </tr>
        <tr>
            <td>MESH</td>
            <td>Message Exchange for Social Care and Health</td>
            <td>A software system that provides the ability to share data directly between health and care organisations and is the nationally recognised mechanism for this method of data sharing.</td>
        </tr>
        <tr>
            <td></td>
            <td>Pathology Laboratory</td>
            <td>A laboratory where tests are carried out on clinical specimens to obtain information about the health of a patient to aid the diagnosis, treatment, monitoring and prevention of disease. The terms pathology laboratory and laboratory are used interchangeably throughout this implementation guide.</td>
        </tr>
        <tr>
            <td>PBCL</td>
            <td>Pathology Bounded Code List</td>
            <td>Originally, a subset of Read v2 codes for use in laboratory to GP practice messaging. Semantically equivalent <b>SNOMED PBCL</b> concepts have since been created.</td>
        </tr>
        <tr>
            <td>PMIP</td>
            <td>Pathology Messaging Implementation Programme</td>
            <td>An implementation programme that was established to support the adoption of the <b>PMIP EDIFACT (NHS003)</b> messaging specification.</td>
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
            <td>SNOMED CT concepts representing laboratory test request and test result codes, published as two SNOMED CT reference sets:<br><br>
                <ul>
                    <li>PaLM (Pathology and Laboratory Medicine) procedure simple reference set - containing laboratory test request codes</li>
					<li>PaLM (Pathology and Laboratory Medicine) observable entity simple reference set - containing laboratory test result codes</li><br><b>SNOMED PaLM</b> has replaced the <b>UTL</b>.
            </td>
        </tr>
        <tr>
            <td></td>
            <td>SNOMED PBCL</td>
            <td>SNOMED CT concepts that are semantically equivalent to <b>PBCL</b> codes.</td>
        </tr>
        <tr>
            <td></td>
            <td>Test Group</td>
            <td>Used within this implementation guide to denote a set of related tests, for example a Full Blood Count. Test groups are often referred to as batteries, panels or profiles.</td>
        </tr>
        <tr>
            <td>UTL</td>
            <td>Unified Test List</td>
            <td>SNOMED CT concepts representing laboratory test request and test result codes. The UTL has been replaced by <b>SNOMED PaLM</b>. </td>
        </tr>
    </tbody>
</table>