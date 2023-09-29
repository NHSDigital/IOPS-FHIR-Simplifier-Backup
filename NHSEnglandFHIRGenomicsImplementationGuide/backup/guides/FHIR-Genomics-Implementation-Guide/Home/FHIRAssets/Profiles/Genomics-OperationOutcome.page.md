## {{page-title}}

The Genomics OperationOutcome is the same as that profiled for the UKCore.

The profile for the UKCore-OperationOutcome is provided below for completeness.

It is expected that all issue codes raised by the Genomic Medicine Service will fall under existing codes boud in the below profile. If further codes are needed, these will be promoted to UK Core for release in a future ballow/sprint

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome) | [UKCore]() | trial-use |

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
            {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/OperationOutcome}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:OperationOutcome-Success}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
    </div>
</div>