## AllergyIntolerance Profiles

TODO: Project must be set to a specific FHIR version, therefore there will be issues rendering on or the other profile.  Currently set to R4, other rendering issues with the CareConnect resource on top of this issue even when set to STU3 Current both profile tabs have R4 AllergyIntolerance.{: .alert .alert-warning}

TODO: Simplifier doesn't render diff blocks for markdown, therefore using html version of the markdown file which is a bit messy.  Would be worth looking into what simplifier supports in terms of markdown, documentation seems a bit light.{: .alert .alert-warning}

This page provides the STU3 CareConnect and UKCore profile of the AllergyIntolerance resource and a generated StructureDefinition diff.

<div class="nhsd-!t-margin-bottom-6">
<ul class="nav nav-tabs" role="tablist">
   <li role="presentation" >
      <a href="#CareConnect" role="tab" data-toggle="tab">CareConnect</a>
   </li>
   <li role="presentation">
      <a href="#UKCore" role="tab" data-toggle="tab">UKCore</a>
   </li>
   <li role="presentation">
      <a href="#CareConnect-JSON" role="tab" data-toggle="tab">CareConnect JSON</a>
   </li>
   <li role="presentation">
      <a href="#UKCore-JSON" role="tab" data-toggle="tab">UKCore JSON</a>
   </li>
   <li role="presentation">
      <a href="#Diff" role="tab" data-toggle="tab">Generated Diff</a>
   </li>
</ul>
<div class="tab-content snippet">
   <div id="CareConnect" role="tabpanel" class="tab-pane active">
      <br>
      {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-AllergyIntolerance-1, diff}}
   </div>
   <div id="UKCore" role="tabpanel" class="tab-pane">
      <br/>
      {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, diff}}
   </div>
   <div id="CareConnect-JSON"  class="tab-pane">
      <br/>
      {{json:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-AllergyIntolerance-1}}
   </div>
   <div id="UKCore-JSON"  class="tab-pane">
      <br/>
      {{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance}}
   </div>
   <div id="Diff"  class="tab-pane">
      <br/>
      {{render:Diff-CareConnect-to-UKCore-AllergyIntolerance3to4}}
   </div>
</div>
</div>





<!--
R4: {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, diff}}

STU3: {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1, diff}}
-->





---