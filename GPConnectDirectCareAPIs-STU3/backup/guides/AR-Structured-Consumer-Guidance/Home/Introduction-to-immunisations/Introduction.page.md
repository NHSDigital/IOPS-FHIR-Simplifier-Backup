## {{page-title}}
 
==does this need a new sub title?==

We've worked with consumers to help them understand the data they receive from the GP Connect API.  

This has enabled them to process the data and display it to their users in a clinically safe way (complying with [clinical safety standards: DCB0160 and DCB0129](https://developer.nhs.uk/apis/gpconnect-1-6-0/designprinciples_clinical_safety_principles.html)).  

 

We answer some common questions on this page. 

This page is intended to be a live document to support clinical assurance of immunisation records in consuming systems and will be updated as new data is available or new scenarios are identified.  

We welcome feedback to improve the scope and detail of this information and may add further items as appropriate. 

 

**Notes:**  

 

* You should also be familiar with the [implementation guidance](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_immunization.html) for GP System provider population of the resources. 

* We have prepared a set of test records for immunisations to represent a wide variety of examples of how the FHIR&reg; resource may be populated.  

* Consumer test data and hazards are referred to in this guidance and links are provided at the bottom of the page to further information. 

 

==TO DO [note to cover wider context i.e. problem associated]== 

 

==TO DO [Note and link as to how a consumer can give feedback / raise issue to include]== 

 

## Contents 

 

==TO DO - Needs populating== 

 

### What is immunisation? 

 

> Immunisation is the process by which an individual’s immune system becomes fortified against an agent (known as the immunogen). 

 

Immunisation is the process by which an individual’s immune system becomes fortified against an agent (known as the immunogen). 

 

When this system is exposed to molecules that are foreign to the body, called non-self, it will orchestrate an immune response, and it will also develop the ability to quickly respond to a subsequent encounter because of immunological memory. This is a function of the adaptive immune system. Therefore, by exposing a person to an immunogen in a controlled way, the person’s body can learn to protect itself: this is called active immunisation. 

 

### What is a vaccination? 

 

> Vaccination is the administration of a vaccine to help the immune system develop protection from a disease. 

 

Vaccination is the administration of a vaccine to help the immune system develop protection from a disease. Vaccines contain a microorganism or virus in a weakened or killed state, or proteins or toxins from the organism. In stimulating the body’s adaptive immunity, they help prevent sickness from an infectious disease. When a sufficiently large percentage of a population has been vaccinated, herd immunity results.  

 

The effectiveness of vaccination has been widely studied and verified. Vaccination is the most effective method of preventing infectious diseases; widespread immunity due to vaccination is largely responsible for the worldwide eradication of smallpox and the elimination of diseases such as polio and tetanus from much of the world. 

 

### What immunisation data is GP Connect sending? 

 

In GP Connect, what is sent in the `Immunization` resource is: 

- The event of a patient being administered a vaccination 

 

    OR 

- Where there is an intention to administer a vaccine which does not occur 

 

This may be: 

- A contemporaneous record by the HCP (the one administering the vaccination or another member of the practice staff recording the event directly on behalf of the clinician) 

    OR

- It may be a record of an immunisation administered elsewhere as reported to the registered GP practice by: 

    - The patient 

    - A carer 

    - A guardian 

    - Another representative of the patient 

    - Another healthcare provider 

A record of an immunisation may be created as part of a scheduled programme of immunisations such as childhood immunisations, seasonal influenza vaccination or in response to specific circumstances (for example, prior to travel, disease outbreak or occupational risk). 

 

**SCENARIO:** If a vaccination is recorded as an issued medication, the details of the issued medication are not included in the immunisations response. The medication details **MUST** be sent as medication resources (if the consumer requests medications). This may be in addition to an immunisation resource for the event of the vaccination administration, depending on how the immunisation event was recorded.

### Using the procedure code 

> **What**: GP Connect, uses the vaccination procedure code to denote the vaccine being administered. The vaccination procedure code is a mandatory element. The vaccine product code will often be a `nullFlavor` code, but the actual vaccine product **MUST** be included if it is available. 

> **Why**: GP clinical systems do not all record the full vaccine product (dm+d code) for an immunisation. GP clinical systems often record the type of vaccine administered as opposed to the vaccine product. This may be as a procedure code or a local code which can be mapped to a procedure code. 

### Vaccinations that were not given 

> **What**: Consumers should be aware that the presence of a vaccination not given record is only in relation to an intended vaccination event on a given day - that is, it is not stating the vaccination has definitely never been given. 

> **Why**: GP clinical systems may capture details of circumstances where an immunisation has not been given but there was an intention to. This version of the specification supports inclusion of intended vaccinations which were not given as defined by Digital Child Health. For details of the requirements see National Events Management Service - Vaccinations or versions as subsequently published. If the GP clinical system holds a coded record of an intended, not given vaccination which is either outside of the scope of the ‘not done’ situation codes or the required code is not available, then the coded information should be included in an uncategorised data response. 

#### Populating elements for an immunisation not given 

Specific rules are applied to the population of some of the elements where the record is for an intended immunisation which was not given. A few of these are highlighted here. 

The provider **MUST** populate elements as described below when sending details of immunisations not given within the immunisation resource. 

`extension[vaccinationProcedure]` **MUST** be the SNOMED CT ‘not done’ situation code for the vaccination which was intended but did not happen 

`notGiven` **MUST** be `true`

`explanation.reasonNotGiven` **SHOULD** be included with the appropriate code for the reason the vaccination did not happen 

See [immunization](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_immunization.html) for full details of the elements. 

#### Consumer handling of immunisations not given 

Consumer systems are to determine whether to request details of immunisations not given. A consumer system which requires not given immunisations **MUST** request this by specifying the part parameter. The default is to return given immunisations only. 

Where a consumer system has requested immunisations not given, it **MUST** ensure that the not given data remains clearly distinct from given vaccinations. The consumer **MAY** need to handle `explanation.reasonNotGiven` alongside the “not done” code to provide the classified reason the vaccination was not given. 

### Additional information about vaccinations 

The above section addresses circumstances where an immunisation is not given at the point of intending to give the vaccine. GP Systems may capture other coded information relating to vaccinations other than the administration of the vaccine in an immunisations feature / module / categorisation.

Examples are information regarding: 

- Consent 

- Dissent 

- Invitations for vaccination 

- Etc. 

==Where provider categorise such coded information as immunisation data==, then it **MUST** only return it against an immunisation request. GP Connect includes the parameter `includeStatus` to enable the consumer to specify the inclusion / exclusion of this information. See [Retrieve a patient’s](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html) for full details of the parameter use. 

Such coded records **MUST** be included with the immunisation bundle using an observation resource, as defined for uncategorised data.

Records returned against an immunisation request under the scope of this definition **MUST** be:  

- excluded from the records returned for an uncategorised data request  

- included in the immunisations `List`

Consumers should note than GP Systems differ with respect to additional information categorised as immunisations, therefore the same coded data may be returned against an immunisation or uncategorised data request by different provider systems. 

#### Ended records 

Where a GP clinical system allows a consent or dissent to be ended, then the `observation.effective` element **MUST** be populated with a `Period` including the relevant start and end dates. 

This does not apply if the consent or dissent has been ended as “entered in error”, in which case the record MUST NOT be included. 

#### Multiple records 

If a patient record has multiple records of consent for a single type of vaccination, for example a dissent and a consent, then all records MUST be included 

 

#### Degraded records 

Any records which the GP clinical systems classifies as an immunisation consent or dissent, but which do not appear in the hierarchies above **MUST** also be included. Where there is an appropriate code which is outside of the stated hierarchy, then that **MAY** be used. Where there is no identifiably appropriate SNOMED CT code for the consent or dissent, then the transfer degraded code **MUST** be used with a text element populated with the original text. 

ConceptId - `196411000000103` DescriptionId - `294691000000115` Description - `Transfer-degraded record entry` 

### Ineffective vaccination 

The Immunization FHIR profile contains elements to denote that a vaccination does not count towards immunity. This could be applied where a vaccination is suspected or found to be ineffective, for example as a result of a product recall or cold chain break. GP clinical systems do not have a standard means to identify an ineffective vaccination. Hence, immunisation records will always be returned as counting towards immunity. 

### Reactions to a vaccine 

Allergic or adverse reactions to an immunisation may be captured in the GP clinical system, but these are not generally directly associated to the immunisation event. It has not been considered reliable to link any allergic or adverse reaction to the immunisation record. Therefore, information about reactions will not be included. For details of allergies or adverse reaction, the  `AllergyIntolerance` resource **MUST** be requested.

### Immunisation schedules and recalls 

The resources required to describe planned immunisation schedules are out of scope for this guidance. According to local practice, immunisations due may be recorded as recalls and retrieved via [Diary entries](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_diaryentry_guidance.html). 

 

### Immunisation notes 

GP systems that support a note entry against the immunisation **MUST** populate the text to the `note` element. Additionally, any other information relevant to the immunisation which does not have a suitable, supported element within the `Immunization` resource **MUST** be populated to the `note` as a key value pair. This includes where there is an element in the profile for the type of information, but the data type is not compatible with the way the data is recorded in the GP system. For example, if the GP system holds the dosage information in a format which does not comply with the `doseQuantity` element’s `Quantity` datatype, then it may be returned as a note key value pair. 

 

### Using the List resource for immunisation queries 

The results of a query for immunisation details **MUST** return a `List` containing references to all `Immunization` and `Observation` resources that are returned.

The `List` **MUST** be populated in line with the guidance on `List` resources. 

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason.code` with the value `no-content-recorded`. In this case, `List.note` **MUST** be populated with the text ‘Information not available’. 

## Building a user interface 

### Which fields do I need to display to my users? 

The fields you need to display to your users will depend on the use case that your product is built for.

Ultimately it should be the clinicians / users of the application who dictate what it is they need. 

When working with your users to build your application some things to consider are: 

* How can you make the information concise and easy to navigate? 

* What are the key things your users need to know? 

* Do you need to provide any onscreen guidance to explain the information being conveyed? 

* Will the application have different use cases that need different views of the data? 

The better you understand how the application will be used, the more appropriate your design can be. 

==[add mockup: who, what imm, when, notes. Starting point may be NHS app. Note to assess / customise by use case]== 

#### GP Connect test data examples 

All the items in the test record should be used to evaluate your user interface.  

This guidance may assist with specific use cases / scenarios by identifying specific records to utilise for given requirements, but you should utilise all the records to prove your user interface. 

#### Associated hazards 

[Back to top](#contents) 

## Understanding the immunisation records 

### What does an immunisation resource represent? 

GP Connect uses the FHIR immunization resource specifically to carry records of a vaccination having been administered. 

The objective of the vaccination will be to achieve a patient immunity, but the data only states that a vaccine has been administered and does not inform whether the intended immunity is achieved. 

The data must only be presented or interpreted in this way. 

#### GP Connect test data examples 

==Not applicable== 

#### Associated hazards 

==Hazard 21== 

[Back to top](#contents) 

### Will the record contain the vaccine product administered or the type of vaccination?

GP connect requires all providers to supply the SNOMED CT procedure code for the vaccination using the `vaccinationProcedure` extension. 

Where the GP system records a vaccine product in the vaccination record then it may also include the product using the `vaccineCode` element. 

The `vaccineCode` is a mandatory element in the immunization profile so, where only the procedure code is captured, a null flavour code will be returned for the product. 

==[Revise text along lines of below]==  

You may receive records where the original text differs significantly from the term text for the procedure code. 

You should always present the original text, but should also make the SNOMED term text readily available to the user. 

See [codeable concept guidance]==(LINK URL)== for more detail. 

==-- [Remove] You may also receive records where the procedure code provided is for the type of vaccination, but the entered text is a vaccine product name.== 

#### GP Connect test data examples 

==Pending additional suppliers.== 

Procedure code, no product detail 

- Administration of tick-borne encephalitis vaccine 

Procedure code, with different user entered text 

- User entered: Avaxim 1 (Procedure: Administration of first dose of paediatric hepatitis A vaccine)== 

#### Associated hazards 

==Hazard 21, 59== 

[Back to top](#contents) 

### Will vaccines administered outside of the GP practice be included? 

There may be records of vaccinations which were not administered by the registered GP practice. 

These may be the result of integration with other systems, patient reported vaccinations, paper records, etc. 

We cannot guarantee all vaccination records are captured in the GP record or that the record is up to date, so consumers must not portray the information as a complete record of vaccination. 

We support identification of vaccinations as secondary records (administered elsewhere) through the primarySource and reportOrigin elements, but GP Systems do not fully support this attribution and the default value for primarySource is true. 

#### GP Connect test data examples 

==Pending additional suppliers.== 

==All records use the same format at in the current test data.== 

#### Associated hazards 

[Back to top](#contents) 

### Will the date of the vaccination always be accurate? 

The date of the vaccination being administered should be as accurate when it was administered by the practice, but records can be recorded from other sources and then the date may be less accurate. 

The date provided is the date to which the vaccination is attributed in the GP record. 

This could represent the date entered or the best recollection of someone reporting the vaccination. 

Where there is some uncertainty as to the exact date, this may be indicated by a partial date or the date element being absent. 

#### GP Connect test data examples 

==Partial date==

- Seasonal influenza vaccination (month / year) 

- First hepatitis B vaccination (year only) 

==Date absent==

- Second meningitis C vaccination

#### Associated hazards 

[Back to top](#contents) 

### Will I know if the patient has refused a vaccine or types of vaccines? 

We may include records relating to consent or refusal of vaccines. 

This could include multiple records for a single type of vaccine e.g. a refusal and a consent. 

Other vaccination related information may also be included with refusals beyond consent or refusal, see ==[Search filters](#Search-filters).== 

If you wish to receive this information, then you must ensure that the correct filter parameters are applied as this is optional data. 

You must also be aware that GP Systems may not categorise all immunisation refusal or dissent records as vaccination information, so coded records of refusal may only be present in the Uncategorised Data clinicial area. 

There may also be different ways to capture this information in GP systems and different codes may be used. 

#### GP Connect test data examples 

Consent given examples 

- Consent given for pneumococcal 

Refusal 

- No consent for hepatitis A vaccination 

- MMR vaccination declined 

#### Associated hazards 

==Hazard 16, 59==

[Back to top](#contents) 

### Are vaccines ever recorded as medications in the GP record?

This is not the most common approach to recording vaccinations, but it may occur. 

If a vaccine has been recorded as a medication it will be available in response to a medications request but will not be returned in response to an immunisation request. 

It should be the case that a vaccination procedure is present where a medication has been recorded, but this cannot be guaranteed. 

#### GP Connect test data examples 

==Not applicable.== 

#### Associated hazards 

==Hazards 14 and 16== 

[Back to top](#contents) 

### How do I know if the patient completed the vaccination course or is due further courses of the vaccine? 

GP connect does not require the GP provider systems to store a vaccination protocol and / or associate the administration of a vaccine to a protocol. 

The FHIR profile allows the protocol to be included and this can indicate how many doses make up the vaccination and where each vaccination is in a sequence. 

GP Connect supports these elements but does not require that they are populated and we expect that for the vast majority of records this detail will not be included. 

It will therefore not be possible to be certain where a patient is up to on a vaccination course purely from the information in the response. 

#### GP Connect test data examples 

==Not currently applicable.== 

#### Associated hazards 

[Back to top](#contents)

### Are multi-component vaccines provided as a single record for all components or separate records for each component? 

Both formats are supported by GP Connect. 

That is, the same vaccination event may be presented by either method. 

This may be a result of (mostly historic) recording practices or source system design. 

==[Check Vision mapping and export and possibly expand detail]== 

#### GP Connect test data examples 

Vaccinations provided as a single entry for multiple components 

- Measles-mumps-rubella vaccination 

- First diphtheria tetanus and five component acellular pertussis, haemophilus influenzae type b, inactivated polio vaccination 

Multiple component vaccines provided as individual records 

- Not currently included in the test data 

#### Associated hazards 

==Hazard 13, 21, 59== 

[Back to top](#contents)

## Adverse consequences from the vaccination 

### If a vaccination is known to have been ineffective will that be shown against the vaccination entry? 

No.  

The Immunization FHIR profile contains elements to denote that a vaccination does not count towards immunity, but these are not used by GP Connect.  

GP clinical systems do not have a standard means to identify an ineffective or suspected ineffective vaccination.  

Hence, immunisation records will always be returned as counting towards immunity in the FHIR profile definition.

#### GP Connect test data examples

==Not applicable.==

#### Associated hazards

[Back to top](#contents) 

### Will any reaction to a vaccination be included

No.

Allergic or adverse reactions to a vaccine may be captured in the GP clinical system, but these are not generally directly associated to the vaccination event.  

It has not been considered reliable to link allergic or adverse reactions to the vaccination record.  

Therefore, information about allergic or adverse reactions will not be included in the immunization resource.

Details of allergies or adverse reactions can be obtained by requesting the AllergyIntolerance resources. 

#### GP Connect test data examples 

==Not applicable==

#### Associated hazards

==Hazard 16==

[Back to top](#contents)

## Search filters

### How do the data filters work?

We offer two data filters for the immunisations request. 

These are includeNotGiven and includeStatus. 

They are optional and support true / false values. 

If not specified, the default response will apply includeStatus = true and includeNotGiven = false.

==#### GP Connect test data examples==

==#### Associated hazards== 

[Back to top](#contents)

### What information may be returned if I request the immunisation status?

If the includeStatus is not included in the request or it is set to true, then the provider will return all other details it captures and categorises as vaccination information. 

The extent to which a GP system categorises coded data in this way will vary significantly between systems. 

This may include information such as: invitations for vaccination; non-attendence; unfit for vaccination; and dissent to vaccination.

#### GP Connect test data examples

The full scope of records is not covered in the test data set. 

We provide the following selection, but other information may be included as supported by terminology and relating to vaccination or immunisation.

Non-attendance for a vaccination 

- Did not attend first rotavirus vaccination

A contrindication to a vaccine or immunisation 

- Contraindication to live immunisation

Consent / dissent for vaccination 

- Consent given for pneumococcal 

- No consent for hepatitis A vaccination 

- MMR vaccination declined

#### Associated hazards

==Hazard 21, 59==

[Back to top](#contents)

### How does a COVID vaccine appear?

==[TO BE COMPLETED]==

## Quick links

* [Home - clinical test data](https://github.com/nhsconnect/gpc-consumer-support/wiki/Clinical-Test-Data)

* [Hazard log](https://github.com/nhsconnect/gpc-consumer-support/raw/master/test_data_files/GP_Connect_Hazard_Log_Consumers_v0.8_DRAFT.xlsx) 

* [Elements of the `Immunization` profile and how to populate and consume them](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_immunization.html) 

* [FHIR&reg; Immunization examples](https://developer.nhs.uk/apis/gpconnect-1-5-0/accessrecord_structured_development_fhir_examples_immunizations.html)


 