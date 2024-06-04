## {{page-title}}

GP practices receive the majority of the results of investigations which they have requested in the form of the EDIFACT message. These are received into a workflow by the GP system and remain there until they are filed into the patient record by a user.

### EDIFACT

The EDIFACT message was defined by the Pathology Messaging Enabling Project and the specification can be found here listed as [EDIFact Pathology Messaging](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections).

It is a detailed specification and although it does contain some coding the majority of the fields contain text. Some of the text is also heavily formatted. See below example taken from a GP2GP HL7v3 message:

{{render: pathology--structured-text-example--2}}

GP systems are required to maintain the text formatting in order to preserve the meaning. This will also be true of the GP Connect messaging, any structured text from the EDIFACT report imported into the GP system **MUST** be maintained as they are in the GP2GP HL7 message. 

The line separator `\n` **MUST** be used to maintain the original message structure.

### Filing results into the patient record

Filing results into the patient record is the process of integrating results that have been received in an EDIFACT message at the GP practice into the patient record. This is done by a user of the clinical system at the GP practice.

When results are filed by the user it is possible to file the entire report or a ‘test group’.

Results may not always be filed on the day they were received. However, in most GP systems the date the report is filed is the date against which it will appear in the patient record. As such, this date is an important date when moving records between GP systems.

When the results are filed, there is opportunity for the user to provide comments against the report or part of the report that they are filing. In GP systems that allow multiple comments to be added against a test group, test report or test result each comment **MUST** be returned.

GP Connect will return any diagnosticReports that are associated with a patient whether they have been filed or not. In all cases where reports have been filed into the record there will be a ‘Filing comments’ observation this will always have a date indicating when the result/report was filed and details any comments made by the user at the time. If multiple comments are associated to the diagnosticReport the earliest comment indicates the date of the filing.

---