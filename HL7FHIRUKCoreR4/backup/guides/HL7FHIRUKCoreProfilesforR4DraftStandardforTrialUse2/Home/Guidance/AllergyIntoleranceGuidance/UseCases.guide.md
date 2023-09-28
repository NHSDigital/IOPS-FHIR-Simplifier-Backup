## {{page-title}}

The following are expected use cases for the UK Core AllergyIntolerance profile:

- Query for patient allergy information
- Exchange patient allergy information within a FHIR Document or FHIR Message
- Migration of allergies data between systems.

### Use Case: Query

The query against a clinical system or shared record to return recorded allergies as `AllergyIntolerance` resources.

<!--In theory, the `AllergyIntolerance` resource could be implemented as a single instance of the resource per allergy or intolerance. For example, if the patient has one known and recored allergy against a substance, then only one instance of the `AllergyIntolerance` resource exists. An instance of the `reaction` element could be added each time a reaction occurs and is recorded. This would result in a record of the allergy and a history of recorded occurances of a reaction.

However, the above use of the `AllergyIntolerance` resource **is not recommended** when data is held within vendor-centric or regional shared records. It would too complex to ensure only a single instance of the resource exists across all systems. It would be too complex to ensure systems update the instance to record reactions. Recording of allergies and reactions in this way is only feasible when the health eco-system has implemented a national shared allergies record or when allergy records are mastered within patient-centric shared records.

Patient-centric shared records are likely to form part of the strategic vision for the UK Core programme. In such an architecture, all clinical systems would access data from the patient's shared record. This means it would be feasible to ensure only a single instance of a resource, per allergy, exists, which can be updated with instances of recorded `reactions`.

When this resource is implemented within vendor-centric or regional shared records, then consumer systems must expect that multiple instances of these resources may exist per patient, per allergy.-->

Returned results could be ordered by `recordedDate` and/or `lastOccurence`.

Returned results may include multiple instances of the same allergy, as per the causative agent (`code`), but with different `clinicalStatus` values. The newer of such records either by `recordedDate` or `lastOccurence` should be deemed the latest or current record of the allergy.

<!--In all cases, multiple instances may exist, which can be returned to the consumer system either within a **FHIR Bundle** or a **FHIR List**. The UK Core standard does not mandate one method over the other. Consumer systems should cater for both Bundles and Lists.-->

### Use Case: Exchange

For when systems need to exchange allergy information within a point-to-point message. The `AllergyIntolerance` resources can be included within a FHIR Message (within the Bundle), or within a FHIR Document alongside other structured resources and text-based data.

To align with the published NHS Data Strategy, allergy information should not be duplicated between systems. When exchanging allergies data between systems be mindful of whether the receiving system plans to persist the data. If persisted, processes must be put in place to ensure the data is updated if/when the source record is updated.

### Use Case: Migration

When allergy records are migrated between systems, the `AllergyIntolerance` resource could be used as a data migration standard.

Where migrated data is not coded, uses retired / invalidated codes, or coded with a terminology which cannot be mapped to SNOMED-CT, then refer to the guidance on using degraded drug / non-drug allergy codes.

---
