## `event[x]`

<b>Definition:</b><br>

The main message type is held in the mandatory `eventCoding` section which can be subdivided by the optional `reason` codes.

Every code **MUST** have a corresponding `MessageDefinition`.

For example the event code `dispense-notification` has a MessageDefinition of [https://fhir.nhs.uk/MessageDefinition/pharmacy-dispense](https://simplifier.net/guide/DigitalMedicines/dispense-notification). This definition lists the profiles and cardinality of the resources in the message. `eventCoding` and MessageDefinition define the structure of the message. 

---
