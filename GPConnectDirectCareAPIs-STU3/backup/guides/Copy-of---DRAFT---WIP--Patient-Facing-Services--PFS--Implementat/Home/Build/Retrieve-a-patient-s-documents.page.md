## {{page-title}} 

{{render : documents-interactions}}

The process of retrieving a patient's documents is a two-stage process and not a direct interaction.

Initially the consuming system must retrieve the patient's correct identifier from the document's server.

This is because a patient's documents aren't stored directly against their NHS Number, it is an internal identifier that varies between providers.

Once the consuming system has the correct identifier it is now ready to hit the document's endpoint.

Further details can be found in the [API catalogue entry](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-access-record-fhir#get-/documents/Patient/-id-).