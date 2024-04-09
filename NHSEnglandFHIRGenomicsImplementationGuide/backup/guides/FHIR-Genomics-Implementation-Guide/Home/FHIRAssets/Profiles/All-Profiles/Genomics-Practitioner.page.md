## {{page-title}}

Practitioner is not expected to be sent within Test Order or other interactions with the central GMS. Instead, client systems SHOULD strive to reference practitioners via their identifier within a national coding system and display name only. 

The below profile is provided for information, if referencing by identifier is intractable (though repeated issues with requester ability to reference via identifier/code SHOULD be reported to the NHS England Genomic Unit for investigation).

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Practitioner}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Practitioner-LucyHale-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Practitioner.name</td><td>Requestor - Full name, Additional contact - Full name, Patient - GP full name, Previous genomic report - Report performer full name, Previous genomic report - Original requester full name, Previous non genomic report - Report performer full name, Previous non genomic report - Original requester full name</td><td>ORC-12, Additional STF segment (STF-3), possibly referenced from the STF segment for the requester via STF-14, PD1-4.2 and PD1-4.3, OBX-16, ORC-12</td></tr>
                    <tr><td>Practitioner.identifier</td><td>Requestor - Professional registration number, Additional contact - Professional registration number, Patient - GP GMC number</td><td>ORC-12.1, STF-2.1, PD1-4.1</td></tr>
                    <tr><td>Practitioner.identifier.system, Additional contact - Professional registration number type</td><td>Requestor - Professional registration number type</td><td>ORC-12.9, STF-2.3</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```
