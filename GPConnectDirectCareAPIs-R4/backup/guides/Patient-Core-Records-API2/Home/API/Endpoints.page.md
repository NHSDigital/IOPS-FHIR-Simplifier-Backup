## {{page-title}}

#### GET patient summary
Requesting a patient summary

Note: For this example, it is implied that the patient summary conforms to the [HL7 IPS specification](https://hl7.org/fhir/uv/ips/)  where the summary is defined in a Composition resource.
The type element of the Composition resource has been set to a loinc code of 60591-5.


__Endpoint URL:__ GET 'https://api.service.nhs.uk/summary/FHIR/R4/Composition?type=60591-5'


__Response__

Success

HTTP Status Code: 200 OK 

Error


### GET Medicines

Request a list of the patients active medication

__Endpoint URL__ GET 'https://api.service.nhs.uk/medications/FHIR/R4/MedicationStatement?patient=Patient/[Patient ID]'

__Response__


Success

HTTP Status Code: 200 OK 

Error

### GET Allergies

Request a list of patients current allergies

__Endpoint URL__ GET 'https://api.service.nhs.uk/strategicapi/allergies/FHIR/R4/AllergyIntolerance?patient=Patient/[NHS Number]'

__Response__
Success

HTTP Status Code: 200 OK 

Error


### POST endpoint (Create data on a receiving system)

This endpoint is for the purpose of sending post-event data to a healthcare professional that has implemented the API. 

Examples of when it would be used are as follows:

- Notification of a consultation with a General Practitioner outside of a patient's regular practice
- Notification of a consultation with a Community Pharmacist
- Emergency supply of medicines services
- Oral contraception service

FHIR profile

The preferred FHIR resource to be used is the UK Core [Bundle](https://simplifier.net/hl7fhirukcorer4/ukcore-bundle) profile.


_Endpoint URL__ POST 'https://api.service.nhs.uk/strategicapi/discharge/FHIR/R4/Bundle'


__Response__
Success

HTTP Status Code: 201 Created



