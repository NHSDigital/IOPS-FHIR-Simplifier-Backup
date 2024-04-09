## {{page-title}}

The Genomics Questionnaire is currently based on the UKCore resource, without any need for profiling.

The profile for the UKCore-Questionnaire is provided below for completeness.

It is not expected that any Questionnaire resources will be submitted to the central service, instead the GMS solution will contain a library of Questionnaires relevant to Genomics that it can use to validate QuestionnaireReponses (such as the example Record of Discussion Questionnaire).

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Questionnaire](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Questionnaire&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

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
            {{tree: http://hl7.org/fhir/StructureDefinition/Questionnaire, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Questionnaire}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/Questionnaire, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/Questionnaire, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Questionnaire-Genomic-Testing}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Questionnaire-RoD-ConsulteeDeclarationForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Questionnaire-RoD-YoungPersonAssentForm-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':http://hl7.org/fhir/StructureDefinition/Questionnaire'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Questionnaire</td><td>RoD Questionnaire Schema</td><td></td></tr>
                </table>
        </div>
    </div>
</div>