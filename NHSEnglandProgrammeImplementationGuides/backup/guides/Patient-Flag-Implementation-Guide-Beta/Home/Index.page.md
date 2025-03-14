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

---

