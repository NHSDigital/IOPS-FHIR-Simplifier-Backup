---
topic: Profile-Genomics-Questionnaire
issue: Questionnaire
subject: http://hl7.org/fhir/StructureDefinition/Questionnaire
expand: yes
---

## StructureDefinition {{variable:issue}}

The Genomics Questionnaire is currently based on the UKCore resource, without any need for profiling.

The profile for the UKCore-Questionnaire is provided below for completeness.

It is not expected that any Questionnaire resources will be submitted to the central service, instead the GMS solution will contain a library of Questionnaires relevant to Genomics that it can use to validate QuestionnaireReponses (such as the example Record of Discussion Questionnaire).

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Questionnaire&scope=hl7.fhir.r4.core@4.0.1' target="_blank">http://hl7.org/fhir/StructureDefinition/Questionnaire</a> | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
<ul>
<li> {{pagelink:Questionnaire-Genomic-Testing,text:Questionnaire-Genomic-Testing-Example}} </li>
<li> {{pagelink:Questionnaire-RoD-ConsulteeDeclarationForm-Example}} </li>
<li> {{pagelink:Questionnaire-RoD-YoungPersonAssentForm-Example}} </li>
</ul>
</div>

<div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Questionnaire</td><td>RoD Questionnaire Schema</td><td></td></tr>
                </table>
</div>

---
    