---
topic: Profile-England-MessageHeader
---

# StructureDefinition-England-MessageHeader

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandMessageHeader'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'EnglandMessageHeader'
select
	Profile_Purpose: purpose
```


<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-MessageHeader, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Prescription Order</b> - An example to illustrate a message header for prescription order<br>
{{pagelink:Example-England-MessageHeader-PrescriptionOrder}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

### Definition

 The header for a FHIR Message exchange that is either requesting or responding to an action. The reference(s) that are the subject of the action as well as other information related to the action are typically transmitted in a bundle in which the MessageHeader resource instance is the first resource in the bundle.

Messaging middleware systems are expected to use this `MessageHeader` resource to route, deliver and handle messages correctly. 

This profile is not tied to any specific transport/API requirement or clinical requirement. Intermediaries are not expected to perform detailed routing on clinical content.
Some clinical information will be required for routing purposes and this will be held within `eventCoding` and `reason` sections as discussed in the Message Event section below. 
In circumstances where more detailed information is required for routing this **MUST** be carried in the relevant FHIR Resource in the payload only. For example, document types should be recorded in FHIR `DocumentReference.type` and health service/specialty type can be recorded in FHIR `Encounter.serviceType` or ` DocumentReference.context.practiceSetting`.


Systems involved in NHSDigital/UKCore messaging are expected to support this profile only, extensions or derived profiles are permitted but they may only have limited (internal) scope and will not be supported outside of this scope (e.g. externally). 
This resource **SHOULD NOT** be profiled to further define the contents of the resources and <a href='https://www.hl7.org/fhir/messagedefinition.html' target="_blank">FHIR MessageDefinition</a> **MUST** be used instead.

 <b>Comment</b>

 <a name="identifiers"></a>
### identifiers and message timings<a href="#identifiers" title="link to here" class="self-link"><i class="bi-link"></i></a>

FHIR messages have two identifiers: the messageIdentifier of the Message (`Bundle.identifier`) and a messageId (`Bundle.id`) which is used in each transport channel . The messageId should be unique within a each message channel/stream. Whenever a message is resent, the messageIdentifier of the Bundle remains the same, but the messageId may change. The response message has its own unique messageIdentifier, the messageIdentifier of the request message can be referenced in the MessageHeader.response.identifier element.

The `Bundle.identifier`, the messageIdentifier, **MUST** have a UUID value.

Systems may chose to map *X-Request-ID* header to the `Bundle.id`, messageId. If both are supplied to a `$process-message` endpoint it is recommended they hold the same values.

MessageHeader can hold previous and extra messageId's in the {{pagelink:Extension-England-MessageHeaderMessageID}}

<b> Local Part/Addressing (sender and/or destination.receiver)</b>

When exchanging messages between organisations, local references **SHOULD NOT** be used for `sender` and `destination.receiver` references. Local references can make use of the Extension {{pagelink:Extension-England-MessageHeaderLocalPart}}. Messages between Organisations should be directed to the Organisation. The receiving organisation will take responsibility for delivering to the local address. Sending organisations are not expected to be able to deliver to local entities in another organisation/domain/facility. 

This concept is similar to email addresses `local-part@domain` and also HL7 version 2 combination of `Sending/Receiving Application | Sending/Receiving Facility` in the MSH segment.

### Example - Prescription, Pharmacy known

{{render:diagrams-nominatedpharmacy}}

In the example below, the prescriber Taunton and Somerset Foundation Trust (RBA), is sending a message to The Simple Pharmacy (VNE51). The `destination.receiver` and `sender` are references to these organisations.

This message is to be sent via the Electronic Prescription Service, the http address of EPS is held in `destination.endpoint`. Replies to this message can only be received by MESH and the `source.endpoint` is the MESH address of the sending organisation.

EPS will now send this message to the pharmacy. This message is collected by the pharmacy using MESH and so the `destination.endpoint` is now the MESH address of the pharmacy. Replies to this message are sent to EPS and so the `source.endpoint` is now the http address of the EPS **$process-message** endpoint.

### Example - Prescription, Pharmacy not known

{{render:diagrams-noNominatedPharmacy}}

In this example the destination is not known and the message is sent to NHS Digital (X26). 
    
{{render:diagrams-messageids}}

In addition, a FHIR Message Bundle has two important timestamps.

The time of sending the message is captured in the timestamp element
The last time the message was updated (e.g. by storing or modification) is captured in the meta.lastUpdated element.

### From (source and sender) and To (destination)

The *From* is contained in both the `sender` and `source` elements and the *To* is contained in the `destination` array. One source, sender and at least one destination **MUST** be present. 

Messages may be sent over multiple transmission legs (i.e. the first leg uses http and the second MESH). The contents of elements **SHOULD** reflect the current leg only.

- destination.endpoint
- source.endpoint
- MessageHeader.extension(messageId)

 Endpoints **MUST** point to valid endpoint uri's on each leg of the messages journey, they may not refer to inaccessible endpoints on other legs. See also the destination section below.
 
 ---