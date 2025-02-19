## Introduction

The FHIR® Patient Flags API has been developed by NHS England. The API aims to better support the delivery of care by opening up nationally stored information and data that patients want to share with healthcare professionals.

The vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within UK health and social care.

## Programme Mission

NHS England, in partnership with patient and carer groups and other key stakeholders are working to develop a national Patient Flags service which will be available to organisations providing direct care to the patient. The flag will be visible from when the patient is referred, registers for care or presents in an emergency.

<a name="pf-key-purposes"></a>
It will collate and present information about the patient that should be known by the clinician or care team in order to provide more effective care.

Current information included in the Patient Flags service is:

* Reasonable adjustment information
* Female genital mutilation risk information
* Child Protection Information System

### Reasonable adjustment information
Reasonable adjustment information can indicate the patient’s key impairments (as defined in the [Equality Act 2010](https://www.gov.uk/guidance/equality-act-2010-guidance)) across areas including learning, mobility, mental health, social or behavioural to make receiving organisations understand that the patient should be considered for adjustments to care. The flag can also indicate key potential reasonable adjustments such as the need for accessible information, carer involvement, priority appointments or other adjustments to care.

<a name="ra-key-purposes"></a>
Key purposes of the Reasonable Adjustment Flag include: 

* identifying a patient may require services to be adjusted  
* identifying when patients with specific impairments present for care (learning impairments, behavioural impairments or any other impairment in line with the disability protected characteristic of the [Equality Act (2010)](https://www.gov.uk/guidance/equality-act-2010-guidance)). 
* ensuring the key information is shared consistently across health and care – wherever the patient is treated. 
* ensuring that the information is clearly visible in clinical systems 

### Female Genital Mutilation
Share female genital mutilation (FGM) information for children under 18 with relevant NHS professionals across England using our Female Genital Mutilation - Information Sharing (FGM-IS) FHIR API

<a name="fgm-key-purposes"></a>
Key purposes of the Female Genital Mutilation - Information Sharing include:

Authorised healthcare workers can:

* query to determine if a patient has a FGM family history indicator
* create a FGM family history indicator for a patient
  * SHALL be gender ‘female’, ‘unknown’ or indeterminate’ according to PDS
  * SHALL be under the age of 18 according to PDS
  * SHALL not already have a FGM family history indicator on FGM-IS
  * SHALL have a verified NHS number
* delete a FGM family history indicator for a patient

The FGM Flag record contains:

* an indicator that a child with female genitalia has a family history of FGM
* the date that the FGM assessment was carried out

### Child Protection - Information System

The Child Protection Information Sharing (CP-IS) initiative aims to share information between NHS clinicians and Local Authority social care practitioners relating to children with either Child Protection, Looked After or Unborn Child care plans.

Relevant data is uploaded to NHS Spine by a Local Authority system where it can be queried by NHS clinicians/practitioners. A response is returned to the practitioner showing any plans in existence for the specified NHS number and also the details of any device or person who has previously submitted a query against that NHS number. Further details of the API design are available.

## Use cases

Current uses are:-

 - As a practitioner at an unscheduled care setting, i can look up whether a patient has a child protection plan (looked after child, Unborn child subject to child protection plan)

 CP-IS has been extended to scheduled care settings:

 - A clinician seeing a child/pregnant woman for scheduled care wishes to know if the child has a care plan, in order to provide contextual care for that person, without alerting the social worker.

## Purpose

 Authorized healthcare workers can:

- Query to check if a child has a Child Protection Plan, including:
  - Looked-After Child (LAC) status
  - Unborn child subject to a protection plan
- Retrieve details of the responsible Local Authority for further action

---

