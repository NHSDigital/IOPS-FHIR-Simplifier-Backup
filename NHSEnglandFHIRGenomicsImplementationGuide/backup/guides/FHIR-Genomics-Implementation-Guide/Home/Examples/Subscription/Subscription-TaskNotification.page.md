---
expand: yes
---

## {{page-title}}

Example of a Subscription resource for setting up alerting when a Task is assigned to an organization. NOTE: In future, owners will be referenced by identifier rather than using resource references (see {{pagelink:Genomics-Task}} for details). The exact subscription/notification mechanism used by the central broker is pending testing in the GMS Alpha.

<div class="nhsd-!t-margin-bottom-6">
  <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#JSON-S-TN-E" role="tab" data-toggle="tab">JSON</a>
        </li>
         <li role="presentation">
            <a href="#XML-S-TN-E" role="tab" data-toggle="tab">XML</a>
        </li>
        <li role="presentation">
            <a href="#Tree-S-TN-E" role="tab" data-toggle="tab">Tree</a>
        </li>
  </ul>
    
  <div class="tab-content snippet">
    <div id="JSON-S-TN-E" role="tabpanel" class="tab-pane active">
{{json:Subscription-TaskNotification-Example}}
    </div>
    <div id="XML-S-TN-E" role="tabpanel" class="tab-pane">
{{xml:Subscription-TaskNotification-Example}}
    </div>
    <div id="Tree-S-TN-E" role="tabpanel" class="tab-pane">
{{tree:Subscription-TaskNotification-Example}}
    </div>
  </div>
</div>