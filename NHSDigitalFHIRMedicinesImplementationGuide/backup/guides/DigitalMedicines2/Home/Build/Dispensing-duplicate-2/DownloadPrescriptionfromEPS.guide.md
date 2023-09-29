## Download Prescription from EPS

<br>

{{render:nominatedreleaserequest}}

The prescription needs to be collected by the pharmacy, this is achieved by calling the FHIR Operation {{pagelink:release2}}  with either to release all prescriptions for a pharmacy 
{{pagelink:NominatedPharmacyReleaseRequest-duplicate-2}} 
or to release a specified prescription
{{pagelink:PatientPrescriptionReleaseRequest-duplicate-2}}

### Example - Nominated Pharmacy 

`POST /Task/$release`

Payload to download all uncollected prescriptions for pharmacy with ODS Code of VNE51.

```json
{
    "resourceType": "Parameters",
    "parameter":  [
        {
            "name": "owner",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "VNE51"
            }
        },
        {
            "name": "status",
            "valueCode": "accepted"
        }
    ]
}
```

### Example - Patient Prescription Release Request

`POST /Task/$release`

Payload to download a Patients prescription with token 82D996-C81010-11DB12

```json
{
    "resourceType": "Parameters",
    "parameter":  [
        {
            "name": "owner",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "VNE51"
            }
        },
        {
            "name": "group-identifier",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                "value": "82D996-C81010-11DB12"
            }
        },
        {
            "name": "status",
            "valueCode": "accepted"
        }
    ]
}
```

## Response Payload 

The response from the `$release` will be a [FHIR Bundle](https://www.hl7.org/fhir/bundle.html) with a Http status code of `200 OK`. 

The total number of prescription-order messages returned will be in the `total` element. 
The `identifier.value` is the release reference number and is used for reference in dispense messages.

The `prescription-order` is carried in the `entry[].resource` array. If no prescription-orders are found total and the number of entries will be zero. 
The number of entries and the total will match, paging is not supported in this API. 

The `$release` is not a stateless operation.
The `$release` operation only returns prescriptions that have not been downloaded, when the operation `$release` is called, EPS marks the the prescriptions as downloaded. So when `$release` is called again, any remaining prescriptions not marked as downloaded will be returned. The downloaded status corresponds to a FHIR Task status of `accepted` and businessStatus of `0002 With Dispenser`, prescriptions undownloaded are deemed to have status of `requested` and businessStatus of `0001 To be Dispensed`. 

`prescription-order` examples and documentation can be found here {{pagelink:prescription-order-duplicate-2}}

{{json:Bundle-E9DDBBC4-DA9A-C223-A2E3-909534332C69}}

