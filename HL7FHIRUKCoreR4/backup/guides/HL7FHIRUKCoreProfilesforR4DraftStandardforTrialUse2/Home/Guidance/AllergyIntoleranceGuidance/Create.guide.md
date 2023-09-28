## {{page-title}}

The adoption of a common POST API syntax would allow the same software to, for example, POST a FHIR resource point-to-point to a dispensing system, or a FHIR resource to a shared records service.

### Create using FHIR RESTful architecture

When POSTing a FHIR resource using a RESTful API use;

``` 
POST [base]/{resource}
```

For example;

``` 
POST https://myfhirserver.net/AllergyIntolerance
```

with a body containing a single FHIR resource. Other resources referenced must be referenced with valid identifier values to allow the consumer system to locate those resources from either the same or another FHIR server.

``` json
{
    "resourceType": "AllergyIntolerance",
    "identifier": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
    // etc.
}
```

### Create using FHIR Messaging architecture

When POSTing a FHIR Message use;

```
POST [base]/$process-message
```

with a body containing a FHIR Bundle within which is a FHIR MessageHeader resource and multiple other FHIR resources.

``` json
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
        "resourceType": "AllergyIntolerance",
        "identifier": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
        // etc.
}

```

---