## {{page-title}}

This is a EPS Futures constraint to enforce referenced resources are contaiend within the resource.

See {{pagelink:NHSDigital-MedicationRequest-duplicate-3}} for full details on the resource profile.

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation" class="active">
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
        <div id="Profile" role="tabpanel" class="tab-pane">
            <br />
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-EPSLegal, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane active">
         <br />
         Differential from {{link:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest}} <br>
            <br />
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-EPSLegal, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
{{dict:  https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-EPSLegal, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
         
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest'
for differential.element.constraint
select key, human, severity, expression
```
        </div>
    </div>
</div>


---
<br>