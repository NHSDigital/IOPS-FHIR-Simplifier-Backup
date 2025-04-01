## {{page-title}}

A [resource read](https://www.hl7.org/fhir/STU3/http.html#read) takes the following format:

```
GET [base]/[type]/[id]{?_format=[mime-type]}
```

The returned resource SHALL have an `id` element with a value that is the [id].

Servers SHALL return an `ETag` header with the `version Id` of the resource.

### Available for resources

|Capability|Resource(s)|
|---|---|
|**Foundations**|`Patient`, `Practitioner`, `Organization`|
|**Access Record**|TBC|
|**Appointments**|`Appointment`, `Schedule`, `Slot`, `Location`|

 **Important:** In workshop discussions with all principal GP system vendors it has been agreed that record locking (inside the GP system) will not impact on the ability of clients to query the GP Connect APIs and to obtain the latest saved/committed clinical and administrative data.

### Retrieving a patient resource by logical ID

#### Request

```
GET [base]/Patient/[id]
```

For example:

```
GET [base]/Patient/1A6E1B1C-6340-4663-926C-9CD1306EAAF8?_format=application/xml+fhir
```

 **Tip:** In this example the response format has been specified in the request URL using the `_format` parameter. This could also have been specified using the HTTP Accept header mechanism.

#### Response

```xml
<Patient xmlns="http://hl7.org/fhir">
 <id value="1A6E1B1C-6340-4663-926C-9CD1306EAAF8" />
 <meta>
  <profile value="http://fhir.nhs.net/StructureDefinition/gpconnect-patient-1" />
 </meta>
 <identifier>
  <system value="http://fhir.nhs.net/Id/nhs-number" />
  <value value="9900002831" />
 </identifier>
 <identifier>
  <type>
   <coding>
    <system value="http://fhir.nhs.net/ValueSet/gpconnect-patient-identifier-type-1" />
    <code value="Local" />
    <display value="Local identifier" />
   </coding>
  </type>
  <system value="http://fhir.nhs.net/Id/local-identifier" />
  <value value="L12345" />
 </identifier>
 <name>
  <use value="usual" />
  <family value="Taylor" />
  <given value="Sally" />
  <prefix value="Mrs" />
 </name>
 <birthDate value="1947-06-09" />
 <address>
  <use value="home" />
  <type value="both" />
  <line value="42, Grove Street" />
  <city value="Overtown" />
  <district value="West Yorkshire" />
  <postalCode value="LS21 1PF" />
 </address>
</Patient>
```

---