## StructureDefinition-UKCore-Patient

Defines the constraints and extensions on the <a href="https://simplifier.net/guide/UKCoreDevelopment2/ProfileUKCore-Patient" target="_blank">UKCore-Patient FHIR Profile</a> for the PDS FHIR API.

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:UK.Core.r4@1.4.0/package/UKCore-Patient.json, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:UK.Core.r4@1.4.0/package/UKCore-Patient.json, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent"  style="display:block">
  <h3>Snapshot View</h3>
 {{tree:UK.Core.r4@1.4.0/package/UKCore-Patient.json, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
     {{pagelink:Example-UKCore-Patient}}
</div>

## Conformance Rules for Patient

PDS implementations using UKCore-Patient must support extensions:

https://www.hl7.org/fhir/extension-patient-birthtime.html

https://www.hl7.org/fhir/extension-patient-birthplace.html

{{pagelink:Extension-UKCore-NHSNumberVerificationStatus}}

{{pagelink:Extension-UKCore-DeathNotificationStatus}}

{{pagelink:Extension-UKCore-AddressKey}}

{{pagelink:Extension-UKCore-NHSCommunication}}

{{pagelink:Extension-UKCore-ContactPreference}}

{{pagelink:Extension-UKCore-OtherContactSystem}}

{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator}}

{{pagelink:Extension-UKCore-ContactRank}}

{{pagelink:Extension-UKCore-NominatedPharmacy}}

{{pagelink:Extension-UKCore-PreferredDispenserOrganization}}

{{pagelink:Extension-UKCore-MedicalApplianceSupplier}}
