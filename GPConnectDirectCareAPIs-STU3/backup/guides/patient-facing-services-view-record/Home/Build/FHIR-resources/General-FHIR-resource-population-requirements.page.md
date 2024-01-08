## {{page-title}}

### Population of optional elements

The purpose of GP Connect is to make the patient data stored within the GP systems available externally so that it can be used to help improve the quality of patient care across the NHS. To give patients the best care possible the data made available through the GP Connect API should be as complete as possible. Therefore, it is expected that both provider and consumers:

- **SHALL** populate all the elements within FHIR resources subject to any Capability-specific variance, where data is available within their system irrespective of the cardinality of the elements within the FHIR resource profiles.

As GP Connect has made the FHIR resources open to aid in interoperability this means that there are some elements included in FHIR profiles which are not applicable to our deployment settings, for example ‘specialism’ in the appointment resource. For these elements if the provider or consumer does not have data stored within their system the element will not be populated.

### Use of Must-Support flag

Some resource profiles used in GP Connect make use of the [Must-Support](https://www.hl7.org/fhir/STU3/conformance-rules.html#mustSupport) flag.

Where a Must-Support flag is present on a resource element, a `consumer` system **SHALL** populate the field in the request body if data is available to do so, irrespective of the fact that field cardinality may be `0..1` or `0..*`.

Similarly, `provider` systems **SHALL** populate an element in responses where data is available to do so, irrespective of optional cardinality. When a `provider` system receives data from a consumer for a field marked with the Must-Support flag, the provider system **SHALL** store this data field in such a way that the data element is preserved and the element can be populated in future responses to consumer requests for the resource in question.

If an element within a FHIR profile is marked as must support then all sub elements of that element SHALL also be considered must support. For example, within the GP Connect Appointment profile the booking organization extension is flagged with must support on the extension. This means that the extension and all sub elements within the extension are must support and SHALL be stored in a way that the data is preserved and the booking organization can be populated in future responses to consumers requesting that resource.

For example, see the [Register a patient request body](https://developer.nhs.uk/apis/gpconnect-1-6-0/foundations_use_case_register_a_patient.html#payload-request-body).