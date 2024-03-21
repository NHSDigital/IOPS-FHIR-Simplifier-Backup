## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>
 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Reporting Organisation|1..1|Organization.id<br/>Organization.name|ODS should be used for identifier & name, using the system "https://fhir.nhs.uk/Id/ods-organization-code"
|Requested Test|1..1|ServiceRequest.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "1148754001"<br/>display "Screening for neoplasm"
|Repost Date|1..1|DiagnosticReport.issued|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|Report Type|1..1|DiagnosticReport.code|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "721981007"<br/>display "Diagnostic studies report"
|Report Standard Text|1..1|DiagnosticReport.conclusion|A fixed disclaimer string
|Participant Identifier|1..1|Patient.identifier|The patient identifier used by the screening organisation
|Sample Identifier|1..1|Specimen.identifier|The speciment identifier used by the screening organisation
|Sample Type|1..1|Specimen.type|A fixed value of<br/>system "http://snomed.info/sct"<br/>code "119297000"<br/>display "Blood specimen"
|Sample Collection Date|1..1|Specimen.collection.collectedDateTime|Using the appropriate [dateTime](http://hl7.org/fhir/datatypes.html#dateTime) format
|Requesting Organisation Name|1..1|Organization.name|ODS organization name NHS England. Name fixed to "NHS ENGLAND - X26"
|Requesting Organisation Identifier|1..1|Organization.identifier|A fixed value of<br/>system "https://fhir.nhs.uk/Id/ods-organization-code"<br/>value "X26"
|Requesting Organisation Address|1..1|Organization.address|ODS organization address for NHS England. Address fixed to line "THE LEEDS GOVERNMENT HUB"<br/>line "7-8 WELLINGTON PLACE"<br/>city "LEEDS"<br/>postalCode "LS1 4AP"<br/>country "ENGLAND"
|Requesting Practitioner Name|0..1|Practitioner.name|Name of the requesting practitioner
|Requesting Practitioner Identifier|0..1|Practitioner.Identifier|Identifier of the requesting practitioner
|Test Result (overall)|0..1|Observation.valueCodeableConcept.coding|The cancer signal result <br/>system "http://snomed.info/sct"<br/>See below for SNOMED CT [cancer signal result codes](#CancerSignalResult)
|Test Result Primary Site|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.code "1873921000000106" and Observation.code.coding.display "Multi-cancer early detection highest scored cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|Test Result Secondary Site|0..*|Observation.component.valueCodeableConcept|As part of the Observation for the primary site, that has an Observation.code.coding.code "1873931000000108" and Observation.code.coding.display "Multi-cancer early detection second highest scored cancer signal origin by machine learning-based classifier"<br/>See below for SNOMED CT [body site mapping](#BodySiteMap)
|Lab Comments|0..1|DiagnosticReport.[extension-DiagnosticReport.note].valueAnnotation.text|An extension to hold lab comments
|Performing Lab Name|1..1|Organization.name|Name of Laboratory where the sample was processed
|Performing Lab Director Name|1..1|Organization.contact.name.text|Full name of the Laboratory director of the sample processing lab
|Lab Identifiers|1..1|Organization.identifier|Identifiers that the Lab has been assigned. These may be regulatory body identifiers that regulates labs testing human specimens
|Lab Address|1..1|Organization.address|Address of the lab that performed the sample processing
|Lab Contact Details|1..1|Organization.telecom|Using system "phone" for phone numbers, using system "fax" for fax numbers, using system "email" for email addressed
|Attachment|1..1|DiagnosticReport.presentedForm.data|Attached pdf document in Base64 that the Lab may provide


## <a id="BodySiteMap"></a>Body site mapping to SNOMED CT

Body sites should be drawn from the Body Structure hierarchy within SNOMED ( \< 123037004 \| Body structure (body structure) ). The body structure suspected as part of a multi-cancer early detection test is recorded in the component Backbone element of the Observation resource that is either the primary or secondary recorded site. Sometimes there may be multiple body sites detected for a primary or secondary cancer signals. In these cases, multiple component Backbone elements should be recorded within the Observation.

For example, for a single body site for a cencer signal detected in the prostate, a single Observation.component should be recorded. In the following snippets not all the Observation elements are shown.

### Example of a single body structure recorded
```
{
  "resourceType": "Observation",
  "id": "dacb177a-9501-4dcc-8b22-b941791ae0db",
  "status": "final",
  "code": {
    "coding": [
      {
        "system": "http://snomed.info/sct",
        "code": "1873921000000106",
        "display": "Multi-cancer early detection highest scored cancer signal origin by machine learning-based classifier"
      }
    ]
  },
  "component": [
    {
      "code": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "123037004",
            "display": "Body structure"
          }
        ]
      },
      "valueCodeableConcept": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "41216001",
            "display": "Prostatic structure"
          }
        ]
      }
    }
  ]
}
```
### Example of two body structures recorded
```
{
  "resourceType": "Observation",
  "id": "dacb177a-9501-4dcc-8b22-b941791ae0db",
  "status": "final",
  "code": {
    "coding": [
      {
        "system": "http://snomed.info/sct",
        "code": "1873921000000106",
        "display": "Multi-cancer early detection highest scored cancer signal origin by machine learning-based classifier"
      }
    ]
  },
  "component": [
    {
      "code": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "123037004",
            "display": "Body structure"
          }
        ]
      },
      "valueCodeableConcept": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "89837001",
            "display": "Urinary bladder structure"
          }
        ]
      }
    },
    {
      "code": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "123037004",
            "display": "Body structure"
          }
        ]
      },
      "valueCodeableConcept": {
        "coding": [
          {
            "system": "http://snomed.info/sct",
            "code": "57789003",
            "display": "Structure of urothelium"
          }
        ]
      }
    }
  ]
}
```



## <a id="CancerSignalResult"></a>Cancer Signal Result

|SNOMED CT Code|Display
|--|
|1854981000000108|Multi-cancer early detection signal detected
|1854991000000105|Multi-cancer early detection signal not detected
