---
topic: Profile-Genomics-BodyStructure
issue: BodyStructure
subject: http://hl7.org/fhir/StructureDefinition/BodyStructure
expand: yes
---


## StructureDefinition {{variable:issue}}

The Genomics BodyStructure is currently based on the HL7 international version of the resource as a profile for BodyStructure does not exist in UKCore. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The base BodyStructure resource is provided below for completeness.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/BodyStructure](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/BodyStructure&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

<br> 
<h2 id='non-fql-header'>Usage</h2>
Use of this resource is meant to replace the Genomics extensions for topology and morphology on the Specimen profile
</br>

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}
<br>
<div id="Examples" class="tabcontent">
    <ul>
    <li>
     {{pagelink:BodyStructure-PancreaticTumour}} </li>
    <li>
     {{pagelink:BodyStructure-BodySiteLocationLungs-Example}}
    </li>
    <li>
     {{pagelink:BodyStructure-SpecimenBodySiteLocation-Example}}
    </li>
    </ul>
</div>

<div id="Mappings" class="tabcontent">
            <br>
               <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>BodyStructure.morphology</td><td>Primary Sample - Solid tumour morphology</td><td>Additional SPM-4/5 qualifiers</td></tr>
                    <tr><td>BodyStructure.location</td><td>Primary Sample - Solid tumour histological type (topography)</td><td>SPM-8</td></tr>
                </table>
</div>

---