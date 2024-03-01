## {{page-title}}

The Genomics BodyStructure is currently based on the HL7 international version of the resource as a profile for BodyStructure does not exist in UKCore. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The base BodyStructure resource is provided below for completeness.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/BodyStructure](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/BodyStructure&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

<br> 
Use of this resource is meant to replace the Genomics extensions for topology and morphology on the Specimen profile
</br>

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
            {{tree: http://hl7.org/fhir/StructureDefinition/BodyStructure, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/BodyStructure}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/BodyStructure, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/BodyStructure, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:BodyStructure-PancreaticTumour}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:BodyStructure-BodySiteLocationLungs-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:BodyStructure-SpecimenBodySiteLocation-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':http://hl7.org/fhir/StructureDefinition/BodyStructure'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>BodyStructure.morphology</td><td>Raw specimen/biopsy - Solid tumour morphology</td><td>Additional SPM-4/5 qualifiers</td></tr>
                    <tr><td>BodyStructure.location</td><td>Raw specimen/biopsy - Solid tumour histological type (topography)</td><td>SPM-8</td></tr>
                </table>
        </div>
    </div>
</div>