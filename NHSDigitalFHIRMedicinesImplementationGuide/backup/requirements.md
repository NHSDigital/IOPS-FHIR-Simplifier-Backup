### requirements

| Profile uri |
|--
| https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance | 



<div class="tab">
    <button class="tablinks active" onclick="openTab(event, 'Definition')">Definition</button>
    <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
    <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="Definition" class="tabcontent" style="display:block">

### FHIR RESTful

{{render:https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance}}

### FHIR Messaging

|Mode|Supported Messages|
|--
|receiver| {{pagelink:prescription-order.md}} |
|receiver|{{pagelink:prescription-order-update}}|
|receiver|{{pagelink:prescription-order-response}}|
|receiver|{{pagelink:dispense-notification}}|

</div>
<div id="JSON"class="tabcontent">
  {{json:https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance}}
</div>
 <div id="XML" class="tabcontent">
  {{xml:https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance}}
</div>

