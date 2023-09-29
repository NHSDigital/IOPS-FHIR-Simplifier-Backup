## {{page-title}}

The term 'ingestion' means that the healthcare data being sent via the transport mechanism (ITK3) is automatically understood by the receiver (GP system) and mapped to its internal data model.​

This is also commonly referred to as 'auto-ingestion'; however, it means the same thing.

Using someone’s name, as an example:​

{{render:filing--mapping-fhir-to-internal-data-model}}

<br />

If data isn't auto-ingested, then a person will have to manually copy and paste the incoming data into the supplier system in the patient record.

Historically, ITK3 has been used to transfer unstructured data, that is, HTML or PDF, which have been stored, and rendered as documents.

While this specification uses the same vehicle as those other specifications to transfer healthcare data, <b>it does not allow</b> HTML to be sent within the `Composition.section.text` element, and mandates that structured FHIR be sent in its place - in most cases, using the GP Connect Data model.​

---

