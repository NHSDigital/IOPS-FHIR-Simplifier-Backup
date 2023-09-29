## {{page-title}}

TODO: Project must be set to a specific FHIR version, therefore there will be issues rendering on or the other profile.  Currently set to R4, other rendering issues with the CareConnect resource on top of this issue even when set to STU3 Current both profile tabs have R4 AllergyIntolerance.{: .alert .alert-warning}

TODO: There is an issue with how these StructureMaps need to be loaded to process them with the validator_cli.  The cannonical url must match (and file) must match what is used for the base transform.  This will be covered in the tooling guideance, so it might be ok at a project level to change the URL of the profile transform to the base one, so both can be displayed.{: .alert .alert-warning}

This page provides:  
* A view of the CareConnect AlleryIntolerance profile (TODO see above)  
* A view of the UKCore AlleryIntolerance profile  
* A StructureMap that will transform a CareConnect AllergyIntolerance resource to a UKCore AllergyIntolerance resource  
* The FML that can be used to generate the CareConnect to UKCore StructureMap for AllergyIntolerance
* The StructureMap provided for base transforms from STU3 to R4 for AllergyIntolerance
* The FML that can be used to generate the base STU3 to R4 StructureMap for AllergyIntolerance
* Resource examples
  * An example STU3 CareConnect AllergyIntolerance input resource
  * The corresponding R4 UKCore AllergyIntolerance output resource

aother speling mistak

</br>

<div class="nhsd-!t-margin-bottom-6">
 <a href="http://abroken.link/tonowhere" role="tab" data-toggle="tab">a sppelling misstake with a broken link</a></br>
 <a href="http://abroken.link/tonowhere" role="tab" data-toggle="tab">a sppelling misstake with a broken link</a></br>
 <a href="https://www.google.co.uk/" role="tab" data-toggle="tab">no mistake</a></br>
<ul class="nav nav-tabs" role="tablist">
   <li role="presentation" >
      <a class="active" href="#CareConnect" role="tab" data-toggle="tab" 	tabindex="-1">CareConnect Profile</a>
   </li>
   <li role="presentation">
      <a href="#UKCore" role="tab" data-toggle="tab">UKCore Profile</a>
   </li>
   <li role="presentation">
      <a href="#StructureMap" role="tab" data-toggle="tab">StructureMap</a>
   </li>
   <li role="presentation">
      <a href="#FML" role="tab" data-toggle="tab">FML</a>
   </li>
   <li role="presentation">
      <a href="#BaseStructureMap" role="tab" data-toggle="tab">Base StructureMap</a>
   </li>
   <li role="presentation">
      <a href="#BaseFML" role="tab" data-toggle="tab">Base FML</a>
   </li>
</ul>

<div class="tab-content snippet">
   <div id="CareConnect" role="tabpanel" class="tab-pane active">
      <br>
      {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, hybrid}}
   </div>
   <div id="UKCore" role="tabpanel" class="tab-pane">
      <br/>
      {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-AllergyIntolerance, hybrid}}
   </div>
   <div id="StructureMap"  class="tab-pane">
      <br/>
      {{tree:http://hl7.org/fhir/StructureMap/CareConnectUKCoreAllergyIntolerance3to4}}
   </div>
   <div id="FML"  class="tab-pane">
      <br/>
      {{render:FML-CareConnet-to-UKCore-AllergyIntolerance3to4}}
   </div>
   <div id="BaseStructureMap"  class="tab-pane">
      <br/>
      {{tree:http://hl7.org/fhir/StructureMap/AllergyIntolerance3to4}}
   </div>
   <div id="BaseFML"  class="tab-pane">
      <br/>
      {{render:FML-Base-AllergyIntolerance3to4}}
   </div>
</div>
</div>

-----