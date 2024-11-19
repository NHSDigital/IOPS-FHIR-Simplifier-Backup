---
topic: Profile-UKCore-Organization
issue: UKCore-Organization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization
expand: yes
---

## StructureDefinition {{variable:issue}}

Organization is not expected to be sent within Test Order or other interactions with the central GMS. Instead, client systems SHOULD strive to reference organizations via their ODS code and display name only. 

The below profile is provided for information, if referencing by ODS code is intractable (though repeated issues with requester ability to reference via ODS code SHOULD be reported to the NHS England Genomic Unit for investigation).

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank">https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization </a> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
           <br>
            <ul>
            <li>
                    {{pagelink:Organization-GenomicsLaboratoryHub-Example}}
               </li>
               </ul>
        </div>
        <div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Organization.name</td><td>Requestor - Organization name, Additional contact - Organization name, address and ODS code</td><td>ORC-21</td></tr>
                    <tr><td>Organization.address</td><td>Requestor - Organization address, Additional contact - Organization address</td><td>ORC-22</td></tr>
                    <tr><td>Organization.identifier</td><td>Requestor - Organization ODS code, Additional contact - Organization ODS code, Patient - GP Practice ODS Code, Previous genomic report - Report performer organisation ODS code, Previous genomic report - Original requester organisation ODS code, Previous non genomic report - Report performer organisation ODS code, Previous non genomic report - Original requester organisation ODS code</td><td>ORC-21.10, OBX-23.10</td></tr>
                    <tr><td>Organization.partOf</td><td>PLCM activity - ODS code of commissioning region</td><td>N/A - not in scope for HL7v2</td></tr>
                </table>
        </div>

<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

___
