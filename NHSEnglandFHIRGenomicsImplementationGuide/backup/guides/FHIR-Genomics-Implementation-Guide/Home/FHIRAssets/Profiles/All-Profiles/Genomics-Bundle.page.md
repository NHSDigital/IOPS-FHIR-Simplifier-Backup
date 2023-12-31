## {{page-title}}

The Genomics Bundle is currently pending Clinical and Technical Assurance of the base UKCore resource. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The profile for the UKCore-Bundle is provided below for completeness.

Bundles within Genomics will be limited to Transactions for Test orders and updates.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

<br>

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
        <li role="presentation">
            <a href="#Mappings" role="tab" data-toggle="tab">Mappings</a>
        </li>
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Bundle}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Bundle-MichaelJonesRequest}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Bundle-MichaelJonesSpecimen}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Bundle-MichaelJonesRequest-Minimal}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-NonWGSTestOrderForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-WGSRoD-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-WGSTestOrderForm-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
        </div>
    </div>
</div>