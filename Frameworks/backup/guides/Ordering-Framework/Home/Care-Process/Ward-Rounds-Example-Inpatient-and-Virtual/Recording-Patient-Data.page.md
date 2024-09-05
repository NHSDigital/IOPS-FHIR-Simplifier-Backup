## {{page-title}}

The introduction described recording information using a variety of use cases. We had three types of information being recorded. These are:

- **documents** The original format of these charts. Observations are still likely to occur in this format, due to practical reasons and digitisation of health will store these on Electronic Document Mangagement Systems (EDMS) after scanning. 
- **forms/templates** Many practitioners will now use portable devices to record these observations. These will either be stored as forms in a Electronic Patient Record (EPR) and/or as observation entries in a EPR. Patients may also be asked to perform similar data in At Home Care Settings, i.e. the patient takes an observation from a device and manually enters this into a hospital Personnel Health Record (PHR) application.
- **observation entries** Systems capable of recording individual observations entries will record data this way. Most citizen based apps also record this way.

Common standards for recording this information are:

<table>
  <thead>
    <th>Record Type</th>
    <th>Standards</th>
  </thead>
  <tr>
    <td>
documents 
    </td>
    <td>
The need to store patient documents and images is generally solved either by an internal or external Electronic Document Management System (EDMS). 

A sharing enabled EDMS will often be called an IHE [XDS System](https://wiki.ihe.net/index.php/Cross-Enterprise_Document_Sharing)
    </td>
  </tr>
  <tr>
    <td>
templates/forms/composition 
    </td>
    <td>
    <a href="https://openehr.org/">
openEHR
</a> provides a standard definition of  
 <a href="https://ckm.apperta.org/ckm/templates/1051.57.141">Vital Signs (including NEWS2) Archetype</a> . openEHR definitions are typically used with openEHR based EPR systems. This combination of both record definition and record storage can be useful. 
    </td>
  </tr>
  <tr>
    <td>
observation entries 
    </td>
    <td>
None
    </td>
  </tr>
<table>

<br/>

How observation entries are recorded is not a standardised entity but the structure is fairly standard across many EPR/PHR systems, some of the elements have associated standards:

| Obsevation type | Date and Time | Value | Unit | Entered By |
|--
| In the NHS it is recommended this is recorded using [UK SNOMED CT](https://digital.nhs.uk/services/terminology-and-classifications/snomed-ct). E.g. 927981000000106 Baseline SpO2 | System specific| E.g. 98 | Units often follow [Unified Code for Units of Measure (UCUM)](https://ucum.org/) E.g. % | System specific |

If you are familiar with [HL7 v2](https://en.wikipedia.org/wiki/Health_Level_7) or [HL7 FHIR](http://hl7.org/fhir/R4/index.html), this concept will be familiar. It is present in the HL7 v2 [OBX Segment](https://hl7-definition.caristix.com/v2/HL7v2.5.1/Segments/OBX) and also the [FHIR Observation](http://hl7.org/fhir/R4/observation.html) resource. The UK supplement to FHIR Observation [UKCore-Observation](https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation) brings in the UK SNOMED CT (see code element). 
The EPR requirement to use SNOMED CT is contained in [NHS England SCCI0034: SNOMED CT](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/scci0034-snomed-ct) 

HL7 standards are not definitions of how records should be stored, however they have been used this way, for example, early UK GP Systems were based on HL7 v2 segment models.
