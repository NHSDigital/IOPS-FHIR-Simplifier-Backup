## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

This **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). An identifier scoped by a provider specific namespace **MUST** be included. If there is a lab report ID, and if it is scoped to the NHS PMIP Report Numbers CodeSystem (from [HL7 UK Issued OIDs](https://www.hl7.org.uk/standards/object-identifiers-oids/hl7-uk-issued-oids/)) and it could be used to assist in matching lab reports this **SHOULD** also be included. In this case `identifier.system` would be `urn:oid:2.16.840.1.113883.2.1.4.5.5`.

Where consuming systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://foo.bar/id/diagnostic-report" />
    <value value="dac264ca-cbb2-43b0-b1f9-867901d769b4" />
</identifier>
```

---