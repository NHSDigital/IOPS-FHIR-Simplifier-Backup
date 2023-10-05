## {{page-title}}

The Genomics Subscription is currently pending Clinical and Technical Assurance of the base UKCore resource. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The profile for the NHSDigital/England Subscription is provided below for completeness.

In the Alpha build of the Genomic Medicine Service, MESH/email will be used as the primary notification procedure though a FHIR native solution is being investigated.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.nhs.uk/StructureDefinition/England-Subscription](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.nhs.uk/StructureDefinition/England-Subscription) | [NHSDigital]() | trial-use |

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
            {{tree: https://fhir.nhs.uk/StructureDefinition/England-Subscription, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Subscription}} <br>
            <br />
            {{tree:https://fhir.nhs.uk/StructureDefinition/England-Subscription, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.nhs.uk/StructureDefinition/England-Subscription, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Subscription-DiagnosticReportNotification}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Subscription-TaskNotification}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Subscription-TaskNotification-Minimal}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':https://fhir.nhs.uk/StructureDefinition/England-Subscription'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
    </div>
</div>