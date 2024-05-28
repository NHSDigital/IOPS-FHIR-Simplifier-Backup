## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: This profile is not in scope for iterations 1 and 2, therefore <b>MUST NOT</b> be sent by provider systems, nor ingested by consuming systems. Should the provider (sender) includes this profile in the payload then the consumer (receiver) <b>MUST</b> reject the entire ITK3 payload with the ITK3 acknowledgement response code <b><code>20009</code> - Payload validation failure</b>.
</div>

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#profile-1" role="tab" data-toggle="tab">Profile</a>
      </li>
      <li role="presentation">
        <a href="#dictionary-1" role="tab" data-toggle="tab">Dictionary</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet nhsd-!t-margin-bottom-6">
    <div role="tabpanel" class="tab-pane active" id="profile-1">
        {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Flag-1}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Flag-1}} 
    </div>
  </div>
</div>

---