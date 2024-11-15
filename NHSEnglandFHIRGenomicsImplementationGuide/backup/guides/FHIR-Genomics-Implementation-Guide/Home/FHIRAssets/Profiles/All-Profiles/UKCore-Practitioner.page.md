---
topic: Profile-UKCore-Practitioner
issue: UKCore-Practitioner
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner
expand: yes
---

## StructureDefinition {{variable:issue}}

Practitioner is not expected to be sent within Test Order or other interactions with the central GMS. Instead, client systems SHOULD strive to reference practitioners via their identifier within a national coding system and display name only. 

The below profile is provided for information, if referencing by identifier is intractable (though repeated issues with requester ability to reference via identifier/code SHOULD be reported to the NHS England Genomic Unit for investigation).

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank"> https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner </a> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <table>
                <tr>
                    <td>
                    {{pagelink:Practitioner-LucyHale-Example}}
                    </td>
                </tr>
            </table>
        </div>

 <div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Practitioner.name</td><td>Requestor - Full name, Additional contact - Full name, Patient - GP full name, Previous genomic report - Report performer full name, Previous genomic report - Original requester full name, Previous non genomic report - Report performer full name, Previous non genomic report - Original requester full name</td><td>ORC-12, PD1-4.2 and PD1-4.3, OBX-16, ORC-12</td></tr>
                    <tr><td>Practitioner.identifier</td><td>Requestor - Professional registration number, Additional contact - Professional registration number, Patient - GP GMC number</td><td>ORC-12.1, PD1-4.1</td></tr>
                    <tr><td>Practitioner.identifier.system, Additional contact - Professional registration number type</td><td>Requestor - Professional registration number type</td><td>ORC-12.9</td></tr>
                </table>
        </div>


<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>


---