## {{page-title}}

Most medicines use cases require the clinician to obtain an understanding of the patient's current medication. 

Today, the patient's GP record is the most complete record of current medication. This data is made available in four ways;

1. Directly by the clinical staff within the patient's GP practice
2. In summary form uploaded [in England] to the NHS [Summary Care Record](https://digital.nhs.uk/services/summary-care-records-scr)
3. Via the [IM1](https://digital.nhs.uk/services/gp-it-futures-systems/im1-pairing-integration) pairing integration
4. Via the [GPConnect](https://digital.nhs.uk/services/gp-connect){: .nhsd-a-link } API.

The strategic direction for medicines interoperability is the implementation of regional Integrated Care Systems (ICS) and/or Shared Medication Records. It is expected that every ICS or Shared Medication Record obtains access to the GP medication record, combining that with medicines data coming from other provider systems.

It is expected that Regional Integrated Care Systems (ICS) and/or Shared Medication Records will implement a FHIR query API that can return a FHIR List or FHIR Bundle of `MedicationStatement` resources. It would also be valid to return the transactional FHIR resources of `MedicationRequest` and `MedicationDispense`. See implementation options below.  

<br />

{{ render: use-case-prescribing-system-querying-ics }}{: .img-responsive }

<br />

Applicable FHIR resources: `MedicationStatement`, and optionally `MedicationRequest` and `MedicationDispense`.

### Definition of 'Current' Medication

<!--<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>IMPORTANT:</strong> A definition of what is deemed 'current' has been a challenge for healthcare IT for many years. This implementation guidance only provides a suggested approach. Until a national standard a published, accepted and proven, this guidance is of experimental status.
</div>-->
<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>NEW:</strong> The September 2023 FCI publication for <a href="https://www.bcs.org/media/aepjpxlw/professional-consolidated-medication-record-rendering-guidance-v20-sep-23.pdf">Rendering of a Consolodated Medications Record</a>, includes a definition of "current medication" within Appendix A of their publication.
</div>

A summarised version of the FCI definition is below with references to data items within the FHIR MedicationStatement resource:

**Acute (single issue) Medication is current if:**
- A prescription has been issued with an end of medication period date set (`MedicationStatement.effectivePeriod.end`) but the end date for the medication period has not yet passed.
- If a prescription has been issued within the last 2 years (`MedicationStatement.effectiveDateTime` or `.effectivePeriod.start`), but with no end date.

**Repeat Medication is current if:**
- There is no end date set (`MedicationStatement.effectivePeriod.end`) for the medication period.
- The medication period end date(`MedicationStatement.effectivePeriod.end`) is on or after the index date (e.g. today).
- And in all cases, the authorised date (`MedicationStatement.effectiveDateTime` or `.effectivePeriod.start`) or last issued date (`MedicationStatement.extension:medicationStatementLastIssueDate`) is within the last two years (whichever is later).

#### Where is 'current' determined?

There are two architectural options for where 'current' medication is determined:

1. By the shared record(s) end-point returning 'current' medication. 
2. By the consuming system, querying for medication records from available shared record(s) then applying logic to determine what is 'current'.

For option 1, this would mean all consuming systems see the same 'current' medication. A consuming can always query for all medication if required. A query to an end-point to return only current medication for a given patient may look like this;

```
GET [base]/currentmedication?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|{NHS_Number}
```

For example;

```
GET https://myfhirserver.net/currentmedication?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>NOTE:</strong> Technically the above is not as per the FHIR standard as there is no 'current medication' operation defined within FHIR.
</div>

For Option 2, this would mean each consuming system would deturmine what is deemded 'current', ideally based on the FCI publication, but would allow different systems in different care settings to use their own definition of 'current'. The FHIR standard includes various ways to [search](https://hl7.org/fhir/search.html) for resources. The following search parameters for these resources defined within the FHIR standard could be useful when querying for current medication.

**MedicationStatement**
- subject[patient].identifier
- status (where `active` or `complete`)
- effective (will pick up either effectiveDateTime or effectivePeriod)

For example;

```
GET [base]/MedicationStatement?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254&status=active,complete&effective=ge2020-05-11
```

**MedicationRequest**
- subject[patient].identifier
- status (where `active` or `complete`)
- intent (where `order`) 
- authoredOn

For example;

```
GET [base]/MedicationRequest?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254&status=active,complete&intent=order&authoredOn=ge2020-05-11
```

**MedicationDispense**
- subject[patient].identifier
- status (where `active` or `complete`)
- whenPrepared

For example;

```
GET [base]/MedicationDispense?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254&status=active,complete&whenPrepared=ge2020-05-11
```

#### What type FHIR resources are returned?

There are four architectural options for which FHIR resources are returned:

1. Only `MedicationStatement` resources
2. Only `MedicationStatement` resources but including `basedOn` referenced `MedicationRequest` resources for prescribed medication
3. A combination of `MedicationRequest` for prescribed medication with `MedicationStatement` resources for non-prescription supply
4. A combination of `MedicationRequest` for prescribed medication, `MedicationStatement` resources for non-prescription supply and `MedicationDispense` resources.

The decision for which resources to return will primarily be dictated by what level of data is available to provider systems. The `MedicationStatement` resource can summarise some of the data contained within `MedicationRequest` and `MedicationDispense` resources. For many use cases, the level of detail available within a `MedicationStatement` resource will be sufficient. 

It would be feasible to build an initial implementation of the query for current medication to return only `MedicationStatement` resources. This can be extended in a future release to return the more detailed resources if/when these are required to support additional and more complex consumer use cases.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>NOTE:</strong> Where a response is returned containing no <code>MedicationStatement</code> resource, it should be interpreted as the provider system has no known current medications for the patient recorded. This does not mean that patient is definately not on any medication. Another shared record in another region (or country, i.e. Wales or Scotland) may hold medication records for the patient. There is a SNOMED code for  <a href='https://termbrowser.nhs.uk/?perspective=full&conceptId1=787481004'>787481004 | No known medications (situation)</a> but this is not required nor expected to be supported by provider or consumer systems.
</div>

---
