### DocumentReference Data Mapping

This table specifies the mapping from data requirements to FHIR targets within the UKCore-DocumentReference resource

| Data Requirement  | HL7v3 dt                          | FHIR Target                   | Notes                                                        |
|-------------------|-----------------------------------|-------------------------------|--------------------------------------------------------------|
| Patient NHSNumber | identifier external               | .subject                      |                                                              |
| Event ID          | type II-IG identifier global      | .masterIdentifier.value       |                                                              |
| payloadID         | type II identifier                | .type                         | \{"system": "2.16.840.1.113883.2.1.3.2.4.12", "code": "REPC_MT400101UK06" \} SHOULD be translated to SNOMED CT as per interaction examples             |
| persistenceDate   | date in yyyyMMddhhmmss format     | .content.attachment.creation  |                                                              |
| eventType         | CV-CP field                       | .context.event                |                                                              |
| The SCR document  | xml fragment                      | .content.attachment.data      |                                                              |
