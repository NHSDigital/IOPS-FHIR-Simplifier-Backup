## {{page-title}}

On admission to any secondary/tertiary care setting, a **medicines reconciliation** process is generally undertaken by pharmacists and pharmacy technicians. This process comprises five steps: 
1. Collect an accurate medication history from appropriate sources prior to admission, or had been recently prescribed 
2. Develop a list of medications to be prescribed or review a list of medications which have currently been prescribed
3. Compare the medications on the two lists identifying medications which have not been prescribed, where doses have changed, or new medications have been prescribed
4. Make clinical decisions based on the comparison and the patients current symptoms 
5. Communicate gaps, confirm changes and provide recommendations of the new list to appropriate caregivers and to the patient.

#### Inpatient Admissions

The steps as listed above would be typically undertaken and recorded within the Trust ePMA system. Changes to on-going medication will be recorded within the Trust ePMA system and explained to the patient and other caregivers over the course of the admission and any further changes on discharge.

#### Outpatient Appointment / Treatment

The steps above would be typically undertaken as listed and recorded within the Trust ePMA system.

#### General Practice Transfer / New Registrations

When a patient registers with a GP practice the medicines reconciliation process is supported by the [GP2GP](https://digital.nhs.uk/services/gp2gp){: .nhsd-a-link } service that makes available the patient's GP record from their previous GP practice clinical system. For new patient registrations where there is no existing primary care record, the GP will ask the patient to describe or bring in their current medication.

### Using GPConnect for Medication History

At the time of publication (May 2025) the [GP Connect Access Record: Structured - FHIR API](https://digital.nhs.uk/developer/api-catalogue/gp-connect-access-record-structured-fhir) is the only nationally available API that can return a patient medication record, from the data in the GP record. 

Shared Care Records are now available in some ICB regions, but not all. A likely future will be the implementation of a national Single Patient Record, but this won't be able for some time. Until that time we recommend using GPConnect. The transition from querying GPConnect to querying a Single Patient Record should be straightforward, as logically both act as a single shared record queried with a FHIR API. 

**Note**: GPConnect is based on FHIR STU3, not FHIR R4 UKCore. There is one incompatible feature in the FHIR Dosage structure between FHIR STU4 and R4. The STU3 standard can only convey a single `doseQuantity` whereas R4 can support multiple `doseQuantity` elements. This manifests itself when sharing high risk medication like Methotrexate where good practice requires the quantity to be expressed as an overall strength and quantity of the unit dose form, e.g. `Methotrexate 2.5mg tablets - 2 tablets (5mg) - daily`.

FHIR STU3 (GPConnect) supports a single expression of a `doseQuantity`.

```xml
<!-- Example: for Methotrexate 2.5mg tablets using FHIR STU3 -->
<text value="2 tablet" />
<doseQuantity>
        <value value="2"/>
        <unit value="tablet"/>
        <system value="http://snomed.info/sct"/>
        <code value="428673006"/>
</doseQuantity>
```

FHIR R4 UKCore supports multiple expressions of a `doseQuantity`.

```xml
<!-- Example: for Methotrexate 2.5mg tablets using FHIR R4 UKCore -->
<text value="2 tablet (5 milligram)" />
<doseAndRate>
    <doseQuantity>
        <value value="2"/>
        <unit value="tablet"/>
        <system value="http://snomed.info/sct"/>
        <code value="428673006"/>
    </doseQuantity>
</doseAndRate>
<doseAndRate>
    <doseQuantity>
        <value value="5"/>
        <unit value="milligram"/>
        <system value="http://unitsofmeasure.org"/>
        <code value="mg"/>
    </doseQuantity>
</doseAndRate>
```

#### Querying GPConnect Data

Refer to the GPConnect specification but the query to return medication for a given patient is simple. All medication records can be returned, or medication records from a given date.

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeMedication",
      "part": [
        {
          "name": "medicationSearchFromDate",
          "valueDate": "2024-10-01"
        }
      ]
    }
  ]
}
```

#### Processing GPConnect Data 

Refer to the GPConnect "Medication and Medical Device Resource Relationships" page which describes what would be returned from the above query.

GPConnect returns a FHIR `List` containing FHIR `MedicationStatement` and `MedicationRequest` resources.

The main benefit in using GPConnect to return structured and coded medication records if that the end user does not need to manually re-key medication data into the ePMA system. Consumer systems should strive to allow a medication record to be copied across into the ePMA system via a single user interaction, i.e. a 'click' of a button. If any amendment is required, for example a change in formulation for easier administration while an inpatient, this can then be done within the ePMA system.

A consumer system can consider processing GPConnect data in three ways. This **excludes** the data related to medications that will be recorded in the ePMA system as this data will always be copied across / persisted within the ePMA system. These approaches just relate to handling the GPConnect records. 

(1) **An API-first approach, query and present on-demand, no persistance**

The GPConnect record is retrieved and presented. Medication records to continue and record in the ePMA system are persisted (with or without any adjustments). If the user moves to a different screen in the ePMA system, and returns, GPConnect is queried again and records presented.

(2) **An API-first approach, query and present on-demand, with a temporary cache**

The GPConnect record is retrieved, locally cached and presented. Medication records to continue and record in the ePMA system are persisted (with or without any adjustments). If the user moves to a different screen in the ePMA system, and returns, the data from the cache is used. 

(3) **Query and persist in the local record, only query again after a given time period**

The GPConnect record is retrieved, locally persisted and presented. Medication records to continue and record in the ePMA system are persisted (with or without any adjustments). If the user moves to a different screen in the ePMA system, and returns, the locally persisted data is used and would be valid for the entire episode of care, i.e. until discharge.

#### Presenting GPConnect Data

The consumer system is responsible for presenting the medication record in a way suitable for the end user. This section provides only guidance for the presentation of data.

For the majority of use cases, a chronological (newest first) presentation would be suitable.

*<< A chronological illustration to be added >>*

![](https://media.istockphoto.com/id/1409329028/vector/no-picture-available-placeholder-thumbnail-icon-illustration-design.jpg?s=612x612&w=0&k=20&c=_zOuJu755g2eEUioiOUdz_mHKJQJn-tDgIAhQzyeKUQ= "title")

The NHS England National Care Records Service (previously known as Summary Care Record) presents a chronological GP medication record grouped by the prescribing type for the medication (acute, repeat, repeat dispensing, prescribed elsewhere and stopped).

*<< A grouped and chronological illustration to be added >>*

![](https://media.istockphoto.com/id/1409329028/vector/no-picture-available-placeholder-thumbnail-icon-illustration-design.jpg?s=612x612&w=0&k=20&c=_zOuJu755g2eEUioiOUdz_mHKJQJn-tDgIAhQzyeKUQ= "title")

User research from a few years ago identified that for some use cases it may be benefical to provide an additional view of medication grouped by BNF category.

**Note**: The BNF category cannot be identified purely from dm+d data so an additional data source would be required.

*BNF Categories:*

- Gastro-Intestinal System
- Cardiovascular System
- Respiratory System
- Central Nervous System
- Infections
- Endocrine System
- Obstetrics, Gynaecology and Urinary-Tract Disorders
- Malignant Disease and Immunosuppression
- Nutrition and Blood
- Musculoskeletal and Joint Diseases
- Eye
- Ear, Nose and Oropharynx
- Skin
- Immunological Products and Vaccines
- Anaesthesia
- Preparations used in Diagnosis
- Other Drugs and Preparations
- Dressings
- Appliances
- Incontinence Appliances
- Stoma Appliances

*<< A grouped by BNF category and chronological illustration to be added >>*

![](https://media.istockphoto.com/id/1409329028/vector/no-picture-available-placeholder-thumbnail-icon-illustration-design.jpg?s=612x612&w=0&k=20&c=_zOuJu755g2eEUioiOUdz_mHKJQJn-tDgIAhQzyeKUQ= "title")

---