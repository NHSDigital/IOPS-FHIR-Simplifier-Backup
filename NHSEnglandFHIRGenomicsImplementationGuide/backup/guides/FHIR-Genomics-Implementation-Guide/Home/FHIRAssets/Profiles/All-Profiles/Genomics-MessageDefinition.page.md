## {{page-title}}

Definitional resource, for NHS England GMS internal use only.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.genomics.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current) | [Genomics]() | trial-use |

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
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/MessageDefinition}} <br>
            <br />
            {{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-MessageDefinition-Genomics'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
    </div>
</div>