## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Frequently asked questions related to the GP Connect technical specification
</div>

### Which serialisation format should I choose as an GP Connect API consumer - JSON or XML?

NHS Digital strongly recommend that all consumer suppliers use JSON, for the following reasons:

- All of the GP PCS Suppliers support JSON, whereas they do not all support XML

- JSON is 30% smaller than XML when sent over the wire

- JSON is a MUST requirement across other NHS Digital interoperability programmes, whereas XML is not

For consumers with less experience working with JSON formats, implementation tools in your language of choice simplify the process of producing and consuming FHIR in JSON.

---

### It is not clear which parts of the FHIR® standard are not in scope for the GP Connect programme.

Please refer to the FHIR Out Of Scope section ({{pagelink:Home/Build/FHIR--implementation.page.md}}) for details on what parts of the FHIR standard are currently considered out of scope.

---

### Why does the specification include CRUD interactions especially DELETE when not needed?

The Delete Resource section ({{pagelink:Home/Build/FHIR--implementation.page.md}}) is included for completeness to illustrate how a RESTful API (such as FHIR) is designed to support the basic Create, Update and Delete (CRUD) operations. It is made clear in this section that GP Connect FoT clients and servers are not expected to implement this operation at this stage, but shouldn’t make implementation decisions that preclude the use of the DELETE HTTP verb in the future. It may be the case that the DELETE verb is used in future incarnations of GP Connect. However, the effect of these on the target systems may be a “soft” delete.

---

### Why does the specification mandate support for FHIR functionality that may not be necessary for GP Connect?

In writing the FHIR implementation guidance for GP Connect we have worked hard to cut down the scope of the FHIR standard that needs to be considered when implementing the first tranche of development work. The “FHIR Out Of Scope” section was included to be as explicit as possible what FHIR functionality we don’t need at this stage. However, as with all standards there is a minimal viable subset which we should be looking to support.

---

### Why is support built in for accessing specific resources when the requirement is for the record for a specified patient?

As outlined in the Compartment Based Access section ({{pagelink:Home/Build/FHIR--implementation.page.md}}) the scope of the Patient Compartment in the GP Connect FoT is limited to Appointment access only. Conceptually, any and all resources where the subject of the resource is a patient could be made available. However, this isn’t mandated.

---

### Why does the guidance include support for amendment to appointments?
In one of the workshops there was a discussion around appointment updates being problematic and we did discuss putting them out of scope. However, after wider stakeholder review it was decided that we should look at limiting the scope of updates (rather than removing the requirement all together). Hence, we have decided to allow updating a small subset of fields on the appointment (i.e. appointment reason/description). We feel this strikes the right balance between allowing minor corrections to be made whilst avoiding the added complexity of some update use cases; particularly rescheduling which can arguably be more easily handled by a cancel operation followed by the creation of a new appointment.

---

### Why is resource versioning included as a mandatory requirement?
It is a key principle of the FHIR RESTful APIs that all resources are versioned; without this support no updates to data can ever be safely performed. This is explained in the “Lost Updates” section and “Transactional Integrity” sections of the FHIR standard. Whilst we recognise that it is not necessary to persist versioned access to historical records, it is important that the latest record version can be ascertained. David Hay (Product Strategist at Orion Health) has a blog post on how systems that don’t fully support versions can handle this requirement in a simple and straight forward way.

https://fhirblog.com/2013/11/21/fhir-versioning-with-a-non-version-capable-back-end/

---

### Will it be necessary in all cases to use an NHS service to look up staff/organisation/location information when a supplier may have their own index of this information?

You are welcome to use your own ODS index (that is, to find an organisation by name/address, and so on). However, you will need to perform an SDS lookup using the ODS code to resolve the FHIR endpoint that represents that ODS code for the purpose of exposing the Access Record and Appointment Management APIs.

---

### Why does the guide suggest that all resources should include text in the display property when this information is also in the HTML view?

The display property is relevant to the Appointment Management and Foundations APIs, not the HTML view. More guidance on the use of the display property has been requested by a vendor to facilitate streamlined display of the structured data.

---

### Why is oAuth2 not used?

Authentication will be via mutual TLS/SSL authentication. The JWT web token has been proposed to allow the easy bundling of related authentication details and to eliminate the need for many separate customer headers, or a bespoke GP Connect bundling format to be defined, implemented and maintained.

---

### Why are JSON Web Tokens (JWT) required?

Extra HTTP headers are needed for sending provenance/audit details. Sending this data in a JWT Bearer token (which is simply a fragment of JSON) is an easy way of achieving the communication of this data and various libraries exist to make authoring this content trivial.

---

### Why is NHS Number not being used as the actual ID for the Patient resource?

As outlined in the FHIR standard there is a clear demarcation between business identifiers (such as NHS Number and CHI number) and logical identifiers which are opaque and only guaranteed to be valid on the FHIR server they are served from.

FHIR’s logical IDs are strings which meet the following regex [A-Za-z0-9-.]{1,64} (in the reference implementations) logical IDs are often the physical record identity (for example, a database primary key or a document store guid). So whilst technically a vendor could use the NHS Number as their logical IDs (as it would match the regex above), this won’t be mandated and can’t be relied upon by consumer applications, which will need to resolve the logical ID from the business ID.

This approach is consistent with the FHIR reference implementations and commercial offerings and is in line with what the wider code4health community is asking for.

---

### Why is there to be a centrally-held list of error codes in addition to the standard HTTP response codes?

The list of error codes is intended to allow consumer applications to make sense of errors that the human operator could potentially do something about. We recognise there is a cost-benefit trade-off in this space and will look to only introduce error codes (above that of the base FHIR specification) when they add sufficient value. For example a 400 - Bad Request error code in isolation doesn’t help you determine which input parameter(s) are malformed and similarly a 422 - Unprocessable Entity doesn’t in isolation help you determine which business rule (or integrity constraint) has caused an operation to fail.

Defining a small number of supplementary error codes to be included in the Operation Outcome entity allows sense to be made of these failing interactions (for example, you’ve requested an Appointment to be booked into a slot that is already Busy).

