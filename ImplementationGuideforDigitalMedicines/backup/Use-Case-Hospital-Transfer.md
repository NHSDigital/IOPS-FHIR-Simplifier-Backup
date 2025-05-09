## {{page-title}}

Applicable for the following use cases;
- Internal transfer, to a ward using a different ePMA system.
- Transfer to another hospital, using a different ePMA system.

The most simple implementation of these use cases will be a RESTful `POST` to the destination ePMA [B] system. The FHIR Message posted being a Bundle of `MedicationStatement` resources and related/referenced resources.

Where ePMA [B] does not operate as a FHIR server then an alternative architecture would be for ePMA [B] to query ePMA [A] using `GET` operations.

<br/>

{{ render: use-case-epma-to-epma }}{: .img-responsive }

<br/>

Where more detailed records are required, a `MedicationStatement` can reference a `MedicationRequest` using the `MedicationStatement.basedOn` element. It can reference a `MedicationDispense` using the `MedicationStatement.derivedFrom` element.

The difference between the clinical data shared in a transfer compared to that shared within a discharge process would be the inclusion of medication activity specific to the inpatient treatment, which is not relevant after discharge. For example, painkillers, pre-operative medication etc. These are sometimes described as **ephemeral** medications, i.e. medications that are started during an episode of care and discontinued within that same care episode.

It is not expected that ICS and shared medication records will include ephemeral medication records as these would add unnecessary complexity to the shared record for minimal value. 

Applicable FHIR resources: `MedicationStatement` and optionally `MedicationRequest`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: The data required to be shared for a hospital transfer in addition to the medications data is out of scope for this implementation guide.
</div>

---