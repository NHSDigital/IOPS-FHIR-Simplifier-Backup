## {{page-title}}

<span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">DRAFT</span>
<span class="nhsd-a-tag nhsd-a-tag--bg-light-green">THIS VERSION</span>

<!--[Link to specification](https://simplifier.net/guide/gp-connect--update-record--itk3/Home/Introduction/Release-notes?version=1.1.6-public-beta)-->


<br />

#### Changes


<table data-responsive>
    <tbody>
        <!-- NHS England Terminmology Server -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/The-NHS-England-Terminology-Server}}
            </td>
            <td>
                Provided information about the <a href="https://digital.nhs.uk/services/terminology-server" target="_blank">NHS England Terminology Server</a>.
            </td>
        </tr>
        <!-- Added Urgent meds examples-->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Examples/Urgent-supply-of-prescription-items-service-Example-1}}
                <br />
                {{pagelink:Home/Examples/Urgent-supply-of-prescription-items-service-Example-2}}
            </td>
            <td>
                Added FHIR examples for urgent supply of prescription items.
            </td>
        </tr>
        <!-- Support for the urgent supply of prescription items service -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}
                <br />
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Encounter-1}}
            </td>
            <td>
                Added support for <a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=1577321000000100" target="_blank">1577321000000100 | Community Pharmacist Consultation Service for urgent supply of prescription items (procedure) |</a>
            </td>
        </tr>
        <!-- Updated AllergyIntolerance profile -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-AllergyIntolerance-1}}
            </td>
            <td>
                Corrected profile link to GPC variant of the Allergy/Intolerance profile.
            </td>
        </tr>
        <!-- Created guidance for handling allergies -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/Handling-allergies}}
            </td>
            <td>
                <ul>
                    <li>Created guidamce to support the handling of allergies / intolerances.</li>
                    <li>The guidance aligns with DAPB4013 and FHIR UK Core</li>
                </ul>
            </td>
        </tr>
        <!-- Updated handling observations -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/Handling-observations}}
            </td>
            <td>
                <ul>
                    <li>Added SNOMED triplets for self-reported blood pressure</li>
                    <li>Added information regarding self-reported readings</li>
                    <li>Added support for <code>Observation.valueAttachment</code></li>
                    <li> Guidance added around the handling of an ABPM report</a>
                </ul>
            </td>
        </tr>
        <!-- ampp -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/Handling-medications}}
            </td>
            <td>
                <ul>
                    <li>Removed erroneus reference to AMPP. This specification is designed to be used with AMP only</li>
                    <li>Added guidance around handling no supply reasons</li>
                </ul>
            </td>
        </tr>
        <!-- Contraception type -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/Mapping-PRSB-headings-to-FHIR}}
            </td>
            <td>
                <ul>
                    <li>Removal of "Procedures and therapies - Contraception type"</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

---