## {{page-title}}

Organization is not expected to be sent within Test Order or other interactions with the central GMS. Instead, client systems SHOULD strive to reference organizations via their ODS code and display name only. 

The below profile is provided for information, if referencing by ODS code is intractable (though repeated issues with requester ability to reference via ODS code SHOULD be reported to the NHS England Genomic Unit for investigation).

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Organization}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Home/Examples/Organization/Organization-GenomicsLaboratoryHub-Example.page.md}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Organization.name</td><td>Requestor - Organization name, Additional contact - Organization name, address and ODS code</td><td>ORC-21, STF-9.2</td></tr>
                    <tr><td>Organization.address</td><td>Requestor - Organization address, Additional contact - Organization address</td><td>ORC-22, STF-11</td></tr>
                    <tr><td>Organization.identifier</td><td>Requestor - Organization ODS code, Additional contact - Organization ODS code, Patient - GP Practice ODS Code, Previous genomic report - Report performer organisation ODS code, Previous genomic report - Original requester organisation ODS code, Previous non genomic report - Report performer organisation ODS code, Previous non genomic report - Original requester organisation ODS code</td><td>ORC-21.10, STF-9.1, PD1-4.14, OBX-23.10</td></tr>
                    <tr><td>Organization.partOf</td><td>PLCM activity - ODS code of commissioning region</td><td>N/A - not in scope for HL7v2</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```
