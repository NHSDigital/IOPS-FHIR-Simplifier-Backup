## {{page-title}}

The adoption of a common `POST` API syntax would allow the same software to, for example, `POST` a FHIR resource point-to-point to a dispensing system, or a FHIR resource to a service like the Electronic Prescription Service (EPS), or a FHIR resource to a shared records service. A service like the EPS may require some additional data elements, but the mechanism of posting can be the same, using a different base URL technical end-point.

When `POST`ing a FHIR resource using a RESTful API use;

`POST [base]/{resource}`

For example;

`POST https://myfhirserver.net/medicationrequest`

with a `body` containing a single FHIR resource. Other resources referenced must be referenced with valid `identifer` values to allow the consumer system to locate those resources from either the same or another FHIR server.

```json
{
    "resourceType": "MedicationRequest",
    "identifier": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
    // etc.
}
```

When POSTing a FHIR Message use;

`POST [base]/$process-message`

with a `body` containing a FHIR Bundle within which is a FHIR `MessageHeader` resource and multiple other FHIR resources.

```json
{
  "resourceType": "Bundle",
  "id": "0A1FD9EF-A3D5-4E95-84CD-552070A03083",
  "identifier": {
    "system": "https://tools.ietf.org/html/rfc4122",
    "value": "34470bbf-07cb-4b49-bef9-f958114f821f"
  },
  "type": "message",
  "entry": [
    {
      "fullUrl": "urn:uuid:0A1FD9EF-A3D5-4E95-84CD-552070A03083",
      "resource": {
        "resourceType": "MessageHeader",
        "id": "0A1FD9EF-A3D5-4E95-84CD-552070A03086",
        "eventCoding": { }, // etc.
        "sender": { }, // etc.
        "source": { }, // etc.
        "destination": { } // etc.
        }
    },
    {
      "fullUrl": "urn:uuid:a54219b8-f741-4c47-b662-e4f8dfa49ab6",
      "resource": {
        "resourceType": "MedicationRequest",
        "identifier": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
        // etc.
}
```

---
