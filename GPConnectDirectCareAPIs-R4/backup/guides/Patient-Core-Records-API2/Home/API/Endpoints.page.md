## {{page-title}}

The API would be used for many healthcare interactions and these would depend on the requirements of each use case. The interactions below are some that may be used with the API.





#### 1. GET patient summary
&nbsp;&nbsp; Requesting a patient summary

Note: For this example, it is implied that the patient summary conforms to the [HL7 IPS specification](https://hl7.org/fhir/uv/ips/)  where the summary is defined in a Composition resource.
The _type_ element of the Composition resource has been set to a loinc code of 60591-5.


__Endpoint URL:__ 
> GET https://[[api]]/summary/FHIR/R4/Composition?type=60591-5


__Response__

Success

> HTTP Status Code: 200 OK 

```json
{
  "resourceType" : "Composition",
  "id" : "composition-minimal",
  "text" : {
    "status" : "generated"

  },
  "status" : "final",
  "type" : {
    "coding" : [
      {
        "system" : "http://loinc.org",
        "code" : "60591-5",
        "display" : "Patient summary Document"
      }
    ]
  },
  "subject" : {
    "reference" : "Patient/eumfh-39-07"
  },
  "date" : "2020-12-11T14:30:00+01:00",
  "author" : [
    {
      "reference" : "Practitioner/eumfh-39-07"
    }
  ],
  "title" : "Patient Summary as of December 11, 2020 14:30",
  "confidentiality" : "N",
  "attester" : [
    {
      "mode" : "legal",
      "time" : "2020-12-11T14:30:00+01:00",
      "party" : {
        "reference" : "Practitioner/eumfh-39-07"
      }
    },
    {
      "mode" : "legal",
      "time" : "2020-12-11T14:30:00+01:00",
      "party" : {
        "reference" : "Organization/simple-org"
      }
    }
  ],
  "custodian" : {
    "reference" : "Organization/simple-org"
  },
  "relatesTo" : [
    {
      "code" : "appends",
      "targetIdentifier" : {
        "system" : "urn:oid:2.16.724.4.8.10.200.10",
        "value" : "20e12ce3-857f-49c0-b888-cb670597f191"
      }
    }
  ],
  "event" : [
    {
      "code" : [
        {
          "coding" : [
            {
              "system" : "http://terminology.hl7.org/CodeSystem/v3-ActClass",
              "code" : "PCPR"
            }
          ]
        }
      ],
      "period" : {
        "end" : "2020-12-11T14:30:00+01:00"
      }
    }
  ],
  "section" : [
    {
      "title" : "Active Problems",
      "code" : {
        "coding" : [
          {
            "system" : "http://loinc.org",
            "code" : "11450-4",
            "display" : "Problem list Reported"
          }
        ]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><ul><li><div><b>Condition Name</b>: Acute myocardial infarction of anterior wall</div><div><b>Code</b>: <span>54329005</span></div><div><b>Status</b>: <span>Active</span></div></li></ul></div>"
      },
      "entry" : [
        {
          "reference" : "Condition/eumfh-39-07-1"
        }
      ]
    },
    {
      "title" : "Medication",
      "code" : {
        "coding" : [
          {
            "system" : "http://loinc.org",
            "code" : "10160-0",
            "display" : "History of Medication use Narrative"
          }
        ]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><ul><li><div><b>Medication Name</b>: Simvastatin 40 MG Disintegrating Oral Tablet</div><div><b>Code</b>: <span>C10AA01</span></div><div><b>Status</b>: <span>Active, started 2014</span></div><div>Instructions: Take 40 mg/day</div></li></ul></div>"
      },
      "entry" : [
        {
          "reference" : "MedicationStatement/eumfh-39-07-1"
        }
      ]
    },
    {
      "title" : "Allergies and Intolerances",
      "code" : {
        "coding" : [
          {
            "system" : "http://loinc.org",
            "code" : "48765-2",
            "display" : "Allergies and adverse reactions Document"
          }
        ]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><ul><li><div><b>Allergy Name</b>: No known allergies</div><div><b>Verification Status</b>: Confirmed</div><div><b>Reaction</b>: <span>no information</span></div></li></ul></div>"
      },
      "entry" : [
        {
          "reference" : "AllergyIntolerance/eumfh-39-07-1"
        }
      ]
    }
  ]
}
```

Error

See {{pagelink:Home/Design/Error-Handling}} for more information about representing errors.

---

### 2. GET Medicines

&nbsp;&nbsp; Request a list of the patients active medications

__Endpoint URL__ 
> GET https://[[api]]/medications/FHIR/R4/MedicationStatement?patient=Patient/[Patient ID]

__Response__


Success

> HTTP Status Code: 200 OK 

Error

---

### 3. GET Allergies

Request a list of patients current allergies

__Endpoint URL__ GET https://[[api]]/strategicapi/allergies/FHIR/R4/AllergyIntolerance?patient=Patient/[NHS Number]

__Response__
Success

> HTTP Status Code: 200 OK 

Error

---

### 4. POST endpoint (Create data on a receiving system)

This endpoint is for the purpose of sending post-event data to a system that has implemented the API. 

Examples of when it would be used are as follows:

- Sending of a consultation with a Community Pharmacist to a patients registered practice
- Emergency supply of medicines services
- Oral contraception service encounter shared with a GP practice
- Details of the patient record 

FHIR profile

The preferred FHIR resource to be used is the UK Core [Bundle](https://simplifier.net/hl7fhirukcorer4/ukcore-bundle) profile.


__Endpoint URL__ POST https://[[api]]/strategicapi/discharge/FHIR/R4/Bundle


__Response__
Success

> HTTP Status Code: 201 Created



