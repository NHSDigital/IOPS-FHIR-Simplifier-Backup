## {{page-title}}

The Genomics QuestionnaireResponse is currently based on the UKCore resource, without any need for profiling.

The profile for the UKCore-QuestionnaireResponse is provided below for completeness.

No additional guidance has been provided on this page as there are no Genomic-specific considerations which need to be made. However, all QuestionnaireResponses submitted to the central service SHALL reference a Questionnaire definition in order to aid validation and presentation of the response content.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
            {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-Genomic-Testing}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-ConsulteeDeclarationForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamCDForn-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamYPAForm-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>QuestionnaireResponse</td><td>Record of Discussion</td><td>CON segments</td></tr>
                    <tr><td>QuestionnaireResponse.item.answer</td><td>RoD questions with appropriate linkId: RoD - Patient category, Test type, RoD - Research opt out reason, RoD - Remote consent, RoD - Recording clinician, RoD - Responsible clinician, RoD - Patient choice status, RoD - Has research participation been discussed, RoD - Signature</td><td>CON-16, CON-2, CON-22, CON-10, STF segment attached to CON, CON-19, CON-11, Inferred through CON-12, N/A not in scope for HL7v2</td></tr>
                </table>
        </div>
    </div>
</div>