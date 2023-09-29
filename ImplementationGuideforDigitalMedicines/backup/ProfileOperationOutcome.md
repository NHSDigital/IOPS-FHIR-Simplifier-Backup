# {{page-title}}

<!--// start of code snippet -->
<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#profile-1" role="tab" data-toggle="tab">Profile</a>
      </li>
      <li role="presentation">
        <a href="#dictionary-1" role="tab" data-toggle="tab">Dictionary</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="profile-1">
        {{tree:nhsdigitalspine/nhsdigital-operationoutcome, snapshot}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:nhsdigitalspine/nhsdigital-operationoutcome}} 
    </div>
  </div>
</div>
<!--// end of code snippet -->

In the event of a RESTful interaction or operation failure, an `OperationOutcome` resource is used to convey specific detailed processable error information back to the client as part of the HTTP response.

National FHIR APIs delivered by NHS Digital will use a profiled version of this resource; [NHSDigital-OperationOutcome](https://simplifier.net/guide/nhsdigital/NHSDigital-OperationOutcome-duplicate-2). Local implementations should consider using this resource as it contains a comprehsnive value-set of error codes and would give consistancy between local and national API error handling.

In addition to the mandatory elements, the `OperationOutcome` should contain details of the error code in the `OperationOutcome.issue.details.coding.code` and `OperationOutcome.issue.details.coding.display` fields. 

The `OperationOutcome` should provide additional diagnostic details of the error in the `OperationOutcome.diagnostics` property where such details securely provide additional error context for consumer applications. Patient identifiable data should not be included within this property.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The sections below provide guidance on the error details to be returned in a number of key scenarios.
</div>

---
