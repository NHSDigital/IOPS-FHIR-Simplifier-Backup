## {{page-title}}

Requirements analysis and Professional Record Standards Body (PRSB) documentation identifies a demand for a clear classification structure to the referral details, separating the reason for referral from the service referred to with each having detailed sub-classifications.
GP clinical systems have taken a variety of approaches to the classification of referrals and the FHIR <code>ReferralRequest</code> has multiple elements to support the classification of referrals.

Analysis was undertaken as to whether GP clinical system data structures and recorded data, PRSB definitions and FHIR resources could be aligned and supported by SNOMED CT terminology to achieve a reliable and meaningful classification structure.

The following subsections give an overview of the analysis and conclusions reached by the curation team.

<h3 id="fhir-referral-classification-elements">FHIR referral classification elements</h3>

The <code>ReferralRequest</code> resource has several elements covering the classification of the referral:
- <code>type</code>
- <code>serviceRequested</code>
- <code>specialty</code>
- <code>reasonCode</code>
- <code>reasonReference</code>


<code>serviceRequested</code>, <code>specialty</code>, <code>reasonCode</code> and <code>reasonReference</code> are fairly distinct and may support the separation of the service referred to (serviceRequested and specialty) from reason for referral (reasonCode and reasonReference). 
The FHIR elements may also support the sub-classification of service referred to and reason for referral.
However, the full extent to which the sub-classification could be achieved was not fully investigated for the reason described in the following sections.

<h3 id="gp-clinical-systems">GP clinical systems</h3>

There is limited commonality across GP clinical systems as to the meta data associated with their referral classification.

All GP clinical systems have a READ/SNOMED CT coded field as the main code for the referral. 
This may be constrained to a referral procedure code hierarchy (descendants of <code>3457005 | Patient referral (procedure) |</code>) or open to a much wide selection of codes which can extend beyond the recognised definition of a referral.
GP clinical systems that constrain to the referral procedure codes (for a new referral entry) may contain other codes due to GP2GP transfers or legacy data.

Analysis of a large referral record set across two GP systems providers identified the following common examples for the main coded classification of the referral:

- Orthopaedic referral
- ENT referral
- Refer to physiotherapist
-  Referral to musculoskeletal clinic
- Referral for further care
- Dermatological referral
- Refer for ultrasound investigation
- Referral to community mental health team
- Advice and guidance request sent
- Fast track referral for suspected skin cancer
- 2 week rule referral - upper GI


The main referral code can therefore be either a reason for referral or referred to service and thus does not align distinctly to any of the FHIR elements.

The GP system may have additional non-READ/SNOMED CT coded classification fields with fixed or locally configured valuesets.
These are often optional fields. 
These fields may have valuesets which align to or span reason for referral and referred to service.

<h3 id="referrals-and-snomed-ct">Referrals and SNOMED CT</h3>

The SNOMED CT ‘is a’ hierarchy (<code>3457005 | Patient referral (procedure) |</code>) was considered as a potential valueset for referrals.
It includes pre-coordinated referral concepts of various patterns which span all the classification elements listed above:

- Referral to institution (for example, hospital)
- Referral to speciality (for example, department)
- Referral to specialist (for example, professional)
- Referral to administrative service (for example, diabetic register)
- Referral for procedures
- Referral for findings/disorders
- Referral statuses (for example, referral accepted by, referral cancelled by)

However, whilst terms span the desired classifications, an acceptable structure to separate the terms into the desired classifications was not found.
While these concepts could be formally modelled within SNOMED and classified using description logic, such attributes do not yet exist, and the concepts are ‘primitive’ with minimal (and often approximate) manually assigned is a relationships.

SNOMED content in this area will not support retrieval behaviour, for example:

- <code>183523005 | Referral to gastroenterology service (procedure) |</code> and <code>306308009 | Referral to gastrointestinal surgeon (procedure) |</code> are unrelated
- <code>892201000000106 | Fast track referral for suspected lower gastrointestinal cancer</code> and <code>276401000000108 | Fast track referral for suspected colorectal cancer (procedure) |</code> are siblings rather than the former subsuming the latter
Neither does SNOMED support the inference that ‘Fast track referral for suspected lower gastrointestinal cancer’ is a ‘Referral to gastroenterology service’.


The terminology in its current form is therefore unlikely to support the structured classification (as it crosses over such classification) and is not suited to structured retrieval queries.

<h3 id="classification-design-decision">Classification design decision</h3>

The analysis provided no clear structure to apply to classification of referrals which the current data in GP clinical systems can support.
The referrals SNOMED terminology does not lend itself to give benefit to a structured classification.
The main coded classification of a referral in GP clinical systems does not clearly align to any element of the <code>referralRequest</code>.

It does not seem practical to enforce a structure to the existing data for referral classification.
The <code>reasonCode</code> has been selected for populating with the main coding of the referral because it:

- is a codeableConcept
- supports multiple values
- is more suited to a wide valueset than alternative elements


Providers <strong>MUST</strong> therefore return their main READ/SNOMED CT code for the referral in the <code>reasonCode</code>.
Additionally, providers <strong>MUST</strong> return all other referral classification detail.
Providers <strong>MAY</strong> populate additional detail to the <code>serviceRequested</code>, <code>specialty</code>. <code>reasonCode</code> (in addition to the main referral code), <code>supportingInfo</code> and/or <code>note</code> element(s) as appropriate to the nature of its data.

Consumer systems should be aware that, as a consequence of not constraining the allowable codes, some provider responses may include amongst their coded entries for referrals some codes which may be a reason for referral or do not relate to a transfer of care such as

- Abdominal pain
- Chest pain
- Full blood count (FBC)
- Thyroid Function Test
