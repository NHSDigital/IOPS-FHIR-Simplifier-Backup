### Resource Reference to a resource

FHIR Message Bundles should be self contained and they should not require an external FHIR Server to process the message. In these cases referenced resources should be contained in the Bundle. It is suggested to use UUID references to navigate the resources in the Bundle, mainly to distinguish between resources within the Bundle and externally referenced resources.

```xml
<Bundle xmlns="http://hl7.org/fhir">
  <entry>
    <fullUrl value="urn:uuid:5fe0dde7-2cdc-43c1-b346-11dda63b51d2" />
    <resource>
      <Patient>
        <id value="2245386903" />
        <!-- other patient details for Joe Bloggs -->
      </Patient>
    </resource>
  </entry>
  <entry>
    <fullUrl value="urn:uuid:3e2097b7-3b28-4954-bded-d6af82a10c40" />
    <resource>
      <Medication>
        <id value="87652004" />
        <code>
          <coding>
            <system value="http://snomed.info/sct" />
            <code value="87652004" />
            <display value="Atenolol" />
          </coding>
        </code>
        <!-- other medication details for Atenolol -->
      </Medication>
    </resource>
  </entry>
  <entry>
    <resource>
      <MedicationRequest>
        <subject>
          <reference value="urn:uuid:5fe0dde7-2cdc-43c1-b346-11dda63b51d2" />
          <display value="Joe Bloggs" />
        </subject>
        <medicationReference>
          <reference value="urn:uuid:3e2097b7-3b28-4954-bded-d6af82a10c40" />
          <display value="Atenolol" />
        </medicationReference>
        <!-- other medication request details -->
      </MedicationRequest>
    </resource>
  </entry>
</Bundle>
```

Within EPS the preference is to move to identifer references as this provides the key information a consumer requires. This also avoids large messages exchanging a considerable of reference data. The exception to this is likely to be the `Patient` resource which will normally be included in the FHIR Message Bundle.

FHIR RESTful API's may make references to resources held on FHIR Servers. 

```xml

<MedicationRequest>
  <subject>
    <reference value="https://fhir.midyorks.nhs.uk/Patient/2245386903" />
    <display value="Joe Bloggs" />
  </subject>
  <medicationReference>
    <reference value="https://fhir.midyorks.nhs.uk/Medication/87652004" />
    <display value="Atenolol" />
  </medicationReference>
  <!-- other medication request details -->
</MedicationRequest>

```

Not the use of `baseUrl` / `resource` / `resource.id`. Local references, i.e. referencing a resource on the same server, may omit the `baseUrl`.

```xml

<MedicationRequest>
  <subject>
    <reference value="Patient/2245386903" />
    <display value="Joe Bloggs" />
  </subject>
  <medicationReference>
    <reference value="Medication/87652004" />
    <display value="Atenolol" />
  </medicationReference>
  <!-- other medication request details -->
</MedicationRequest>

```
