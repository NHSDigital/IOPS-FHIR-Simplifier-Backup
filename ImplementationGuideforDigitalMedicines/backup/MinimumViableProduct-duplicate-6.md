## Minimum Viable Product

- [R4 Resource](https://www.hl7.org/fhir/patient.html)
- [UK Core Resource](https://simplifier.net/ukcore-v2/ukcorepatient)

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>MVP</th>
            <th data-no-sort>R4</th>
            <th data-no-sort>UK Core</th>
        </tr>
    </thead>
    <tbody>
        <!-- id -->
        <tr>
            <td>
                <a href="#Elementid6">id</a>
            </td>
            <td>
                <span class="mro-circle required" title="Required"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- identifier -->
        <tr>
            <td>
                <a href="#Elementidentifier6">identifier</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- identifier (nhsNumber) -->
        <tr>
            <td>
                <a href="#Elementidentifier-nhsNumberextension">identifier - nhsNumber</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-times text-danger"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- active -->
        <tr>
            <td>
                <a href="#Elementactive">active</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- name -->
        <tr>
            <td>
                <a href="#Elementname">name</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- telecom -->
        <tr>
            <td>
                <a href="#Elementtelecom">telecom</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- gender -->
        <tr>
            <td>
                <a href="#Elementgender">gender</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- birthDate -->
        <tr>
            <td>
                <a href="#ElementbirthDate">birthDate</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- deceased -->
        <tr>
            <td>
                <a href="#Elementdeceasedx">deceased</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- address -->
        <tr>
            <td>
                <a href="#Elementaddress">address</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- maritalStatus -->
        <tr>
            <td>
                <a href="#ElementmaritalStatus">maritalStatus</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- multipleBirth -->
        <tr>
            <td>
                <a href="#ElementmultipleBirthx">multipleBirth</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- photo -->
        <tr>
            <td>
                <a href="#Elementphoto">photo</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- contact -->
        <tr>
            <td>
                <a href="#Elementcontact">contact</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- communication -->
        <tr>
            <td>
                <a href="#Elementcommunication">communication</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- generalPractitioner -->
        <tr>
            <td>
                <a href="#ElementgeneralPractitioner">generalPractitioner</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- managingOrganization -->
        <tr>
            <td>
                <a href="#ElementmanagingOrganization">managingOrganization</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- link -->
        <tr>
            <td>
                <a href="#Elementlink">link</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
    </tbody>
</table>

---