## {{page-title}}

a) If done in one query this would return everything, no date filter could be applied on medications, observations, investigations, referrals or diary entries:

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeAllergies",
      "part": [
        {
          "name": "includeResolvedAllergies",
          "valueBoolean": true
        }
      ]
    },
    {
      "name": "includeMedication"
    },
    {
      "name": "includeConsultations",
      "part": [
        {
          "name": "consultationSearchPeriod",
          "valuePeriod": {
            "start": "2019-12-21",
            "end": "2020-02-21"
          }
        }
      ]
    },
    {
      "name": "includeProblems"
    },
    {
      "name": "includeImmunisations"
    },
    {
      "name": "includeUncategorisedData"
    },
    {
      "name": "includeInvestigations"
    },
    {
      "name": "includeReferrals"
    },
    {
      "name": "includeDiaryEntries"
    }
  ]
}
```

b) If done in two queries this would be a query for the last three months for observations, medications, investigations, referrals and diary entries and a second query for the last three months’ consultations and all allergies, problems and immunisations:

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeMedication",
      "part": [
        {
          "name": "medicationSearchFromDate",
          "valueDate": "2019-12-21"
        }
      ]
    },
    {
      "name": "includeUncategorisedData",
      "part": [
        {
          "name": "uncategorisedDataSearchPeriod",
          "valuePeriod": {
            "start": "2019-12-21",
            "end": "2020-02-21"
          }
        }
      ]
    },
    {
      "name": "includeInvestigations",
      "part": [
        {
          "name": "investigationSearchPeriod",
          "valuePeriod": {
            "start": "2019-12-21",
            "end": "2020-02-21"
          }
        }
      ]
    },
    {
      "name": "includeReferrals",
      "part": [
        {
          "name": "referralSearchPeriod",
          "valuePeriod": {
            "start": "2019-12-21",
            "end": "2020-02-21"
          }
        }
      ]
    },
    {
      "name": "includeDiaryEntries",
      "part": [
        {
          "name": "diaryEntriesSearchDate",
          "valueDate": "2019-12-21"
        }
      ]
    }
  ]
}
```

AND

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
  {
      "name": "includeConsultations",
      "part": [
        {
          "name": "consultationSearchPeriod",
          "valuePeriod": {
            "start": "2019-12-21",
            "end": "2020-02-21"
          }
        }
      ]
    },
    {
      "name": "includeAllergies",
      "part": [
        {
          "name": "includeResolvedAllergies",
          "valueBoolean": true
        }
      ]
    },
    {
      "name": "includeProblems"
    },
    {
      "name": "includeImmunisations"
    }
  ]
}
```