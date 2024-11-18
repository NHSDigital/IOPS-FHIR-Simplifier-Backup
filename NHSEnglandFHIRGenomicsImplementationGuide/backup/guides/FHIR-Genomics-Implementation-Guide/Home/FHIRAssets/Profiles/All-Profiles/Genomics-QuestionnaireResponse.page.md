---
topic: Profile-Genomics-QuestionnaireResponse
issue: Genomics-QuestionnaireResponse
subject: http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse
expand: yes
---

# {{variable:issue}}

The Genomics QuestionnaireResponse is currently based on the UKCore resource, without any need for profiling.

The profile for the UKCore-QuestionnaireResponse is provided below for completeness.

No additional guidance has been provided on this page as there are no Genomic-specific considerations which need to be made. However, all QuestionnaireResponses submitted to the central service SHALL reference a Questionnaire definition in order to aid validation and presentation of the response content.

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse&scope=hl7.fhir.r4.core@4.0.1' target="_blank">http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse </a> | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}
        
<div id="Examples" class="tabcontent">
<br />
<ul>
<li> {{pagelink:QuestionnaireResponse-Genomic-Testing}} </li>
<li> {{pagelink:QuestionnaireResponse-RoD-ConsulteeDeclarationForm-Example}}</li>
<li> {{pagelink:QuestionnaireResponse-RoD-Example}} </li>
<li> {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamCDForn-Example}} </li>
<li>  {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamFather-Example}} </li>
<li> {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamMother-Example}} </li>
<li> {{pagelink:QuestionnaireResponse-RoD-PheobeSmithamYPAForm-Example}} </li>
</ul>
</div>

<div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>QuestionnaireResponse</td><td>Record of Discussion</td><td>CON segments</td></tr>
                    <tr><td>QuestionnaireResponse.item.answer</td><td>RoD questions with appropriate linkId: RoD - Patient category, Test type, RoD - Research opt out reason, RoD - Remote consent, RoD - Recording clinician, RoD - Responsible clinician, RoD - Patient choice status, RoD - Has research participation been discussed, RoD - Signature</td><td>CON (for OML, included in RoD, referenced from NTE-3)</td></tr>
</table>

</div>

---