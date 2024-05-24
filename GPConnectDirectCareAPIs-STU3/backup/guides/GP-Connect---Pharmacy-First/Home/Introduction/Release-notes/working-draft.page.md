## {{page-title}}

<span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">DRAFT</span>
<span class="nhsd-a-tag nhsd-a-tag--bg-light-green">THIS VERSION</span>

<!--[Link to specification](https://simplifier.net/guide/gp-connect--update-record--itk3/Home/Introduction/Release-notes?version=1.1.6-public-beta)-->


<br />

#### Changes


<table data-responsive>
    <tbody>
        <!-- Updated AllergyIntolerance profile -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-AllergyIntolerance-1}}
            </td>
            <td>
                Corrected profile link to GPC variant of the Allergy/Intolerance profile
            </td>
        </tr>
        <!-- ABPM report -->
        <tr>
            <td class="nhsd-m-table__highlighted-items">
                {{pagelink:Home/Build/Handling-observations}}
            </td>
            <td>
                Guidance added around the handling of an ABPM report within Observation.attachment.
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
                    <li>Removed erroneus reference to AMPP. This specification is designed to be used with AMP only.</li>
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