## {{page-title}}

In order to help consuming systems manage the risk of multiple area searches and to help providers by minimising calls to the API and the volume of data returned we have decided to introduce some predefined searches.

These searches are exceptions to the rules that we have imposed on search parameters and will use combinations of filters that are not available to consumers when building their own searches, see [Not permitted parameter combinations](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html#not-permitted-parameter-combinations) for the full list. These have been created to reduce the burden on suppliers from an API and volume of data perspective while also giving us the opportunity to highlight the clinical risks that are present when these queries are used.

Here we provide the code needed make these requests so consuming systems can pick up and use efficient queries that will pull back a set of data that they are likely to need in one call. We also highlight to them the precise risks involved in the queries and offer advice to help them mitigate these risks.

As consumers build and use the API we will gather feedback about the queries we have defined and change or add to them as necessary. In time we may build a library of searches depending on the demand and how useful suppliers find them.

### Pre-defined search 1 - Last 3 consultations, last 1 years medications, allergies and problems

We have included this search as the last 3 consultations and problems are areas we have had feedback are the most in demand pieces of information after medications and allergies. It is intended to give a good picture of the patients recent GP record without having to return all the data for their medications.

#### Request

A skeleton request is included below consumers just need to insert the correct date and NHS number.

```json
{
  "resourceType":"Parameters",
  "parameter":[
    {
      "name":"patientNHSNumber",
      "valueIdentifier":{
        "system":"https://fhir.nhs.uk/Id/nhs-number",
        "value":"9999999999"
      }
    },
    {
      "name":"includeConsultations",
      "part":[
        {
          "name":"includeNumberOfMostRecent",
          "valuePositiveInt":3
        }
      ]
    },
    {
      "name":"includeProblems"
    },
    {
      "name":"includeAllergies",
      "part":[
        {
          "name":"includeResolvedAllergies",
          "valueBoolean":true
        }
      ]
    },
    {
      "name":"includeMedication",
      "part":[
        {
          "name":"medicationSearchFromDate",
          "valueDate":"today()-365 days"
        }
      ]
    }
  ]
}
```

### Pre-defined search 2 - Last 3 consultations, last 1 years medications, allergies, immunisations, problems and uncategorised data

This query covers all the same data returned in rep-defined search 1 with the addition of immunisations and uncategorised data.

This search is intended to cover common use cases relating to paediatric care where childhood vaccinations and observations may often be required.

#### Request

```json
{
  "resourceType":"Parameters",
  "parameter":[
    {
      "name":"patientNHSNumber",
      "valueIdentifier":{
        "system":"https://fhir.nhs.uk/Id/nhs-number",
        "value":"9999999999"
      }
    },
    {
      "name":"includeConsultations",
      "part":[
        {
          "name":"includeNumberOfMostRecent",
          "valuePositiveInt":3
        }
      ]
    },
    {
      "name":"includeAllergies",
      "part":[
        {
          "name":"includeResolvedAllergies",
          "valueBoolean":true
        }
      ]
    },
    {
      "name":"includeMedication",
      "part":[
        {
          "name":"medicationSearchFromDate",
          "valueDate":"today()-365 days"
        }
      ]
    },
    {
      "name":"includeProblems"
    },
    {
      "name":"includeImmunisations"
    },
    {
      "name":"includeUncategorisedData"
    }
  ]
}
```

### Clinical risk

The clinical risks that are associated with these 2 queries are the same as the risk outlined above.

It can occur if a medication either contained in a consultation or linked to a problem is returned that is more than a year old.

### Mitigations

When processing data that is received consuming systems should exercise caution when processing medication data that is returned as part of a problem or consultation.

If additional medication data than that included in the primary medications list is returned by the query, for instance as a part of a problem or consultation. Then the consuming system **MUST** consider how this is processed and/or displayed to the user.

- It may be best to display the secondary list medication data separately to the medications returned in the main medications list.
- Consumers should consider if there are appropriate places to display prominent/disruptive warnings to their users to ensure that they are aware of any possible gaps in the data.
