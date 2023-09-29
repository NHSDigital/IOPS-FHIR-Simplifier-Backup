## PDS Dispensing Contractors and Nomination

As per current processes, a patient may require prescribed items to be authorised across different prescriptions to allow for dispensing by different dispensing contractors.

Four dispensing site preference codes are defined within EPS {{pagelink:DM-Performer-Site-Type-duplicate-2}}

### Patient Dispensing Nomination

A patient can choose up to three nominated dispensers to cover different contractor types:

- Community Pharmacy
- Appliance Contractor
- Dispensing Doctor

Nomination information is stored in the PDS and is updated using the same update semantics as other aspects of the patient’s demographic record. 

The following is an example of a patients Community Pharmacy, Appliance Contractor and Dispensing Doctor nominations retrieved from the PDS FHIR API.

```json
...
"extension": [
    {
      "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NominatedPharmacy",
      "valueReference": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "Y12345"
        }
      }
    },
    {
      "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PreferredDispenserOrganization",
      "valueReference": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "Y23456"
        }
      }
    },
    {
      "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicalApplianceSupplier",
      "valueReference": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "Y34567"
        }
      }
    }
    ]
    ...
```

Where a nominated dispenser is not available, or the patient does not wish to use their nominated dispenser then this information must be omitted.

The codes used are ANANA/ODS codes and the details of these can be retrieved using a SDS LDAP lookup or by using the FHIR STU3 ODS API https://nhsconnect.github.io/FHIR-ODS-API/ 
For example: to retrieve details of the patients nominated pharmacy (Y12345), the ODS FHIR API Query would be 

```
GET https://directory.spineservices.nhs.uk/STU3/Organization/Y12345 
```

The nominatedPharmacy in {{pagelink:NHSDigital-MedicationRequest-duplicate-3}} does not have to match the nominations above. If the nominations in PDS are incorrect it is recommended these are updated during the prescribing process.