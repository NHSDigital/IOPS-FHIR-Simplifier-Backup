# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> This page is work-in-progress and may be subject to change.
</div>

Infusions are complex because they may be requested in different ways due to different protocols implemented within different Trusts.

The **active ingredient** will always be specified by the prescriber. How the infusion (or injection) is to be prepared may not be. The **diluent** and/or **reconstituting liquid** may be specified or may be left to the pharmacy or ward clinical team.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<strong>IMPORTANT:</strong> The examples on this page are fragments and do not include all data required to be valid FHIR Resources.
</div>

Complete [examples for infusions](DosageExamples-Infusions) are available within the Examples section of this guide.

## Active Ingredient

The active ingredient for the infusion shall be defined as either a `medicationCodeableConcept` or within a referenced `Medication` resource.

For example;

```json
{
  "resourceType": "MedicationRequest",
  "medicationCodeableConcept": {
    "coding": [
      {
        "system": "https://dmd.nhs.uk",
        "code": "774587000",
        "display": "Co-amoxiclav"
      }
    ]
  }
}
```

Or when using a referenced `Medication` resource. Note that this example `MedicationRequest` resource is only a fragment and does not include all required business data.

```json
{
  "resourceType": "Bundle",
  "entry": [
    {
      "resource": {
        "resourceType": "Medication",
        "id": "11dc9519-b6e8-41bb-bce5-f6f724b743bc",
        "code": {
          "coding": [
            {
              "system": "https://dmd.nhs.uk/",
              "code": "774587000",
              "display": "Co-amoxiclav"
            }
          ]
        }
      }
    },
    {
      "resourceType": "MedicationRequest",
      "id": "34eb3c92-76e6-48c2-9691-aa1f0b58369b",
      "medicationReference": {
        "reference": "11dc9519-b6e8-41bb-bce5-f6f724b743bc",
        "type": "Medication"
      }
    }
  ]
}
```

## Diluents

The implementation of infusion protocols within a Trust may or may not require the prescriber to specify the diluent. Where not specified, clinical staff will determine the most appropriate diluent.

Where a diluent is required to be specified, it can be defined as an `ingredient` within a referenced `Medication` resource of the `MedicationRequest`.

Where a diluent and it's strength are to be specified, use the VTM and include a `strength` as per this example.

```json
{
  "ingredient": [
    {
      "itemCodeableConcept": {
        "coding": [
          {
            "system": "https://dmd.nhs.uk",
            "code": "777553004",
            "display": "Sodium chloride"
          }
        ]
      },
      "strength": {
        "numerator": {
          "value": 0.9,
          "unit": "percent",
          "system": "http://unitsofmeasure.org",
          "code": "%"
        },
        "denominator": {
          "value": 1
        }
      }
    }
  ]
}
```

Note there are few use cases when the diluent is recorded without a strength. An example may be `Water for injection` but this is not defined as a VTM (it is just `Water`, which is not the same) so a VMP would always have to be used.

Where more detailed information about the diluent is required, for example, inclusion of the strength and volume, then it is recommended to use a VMP. There is no need to include a `strength` element as the strength is included within the VMP. This works when the required volume also matches that of the VMP. 

For example, I want to specify a diluent of **100 mL of Sodium chloride 0.9%**;

```json
{
  "ingredient": [
    {
      "itemCodeableConcept": {
        "coding": [
          {
            "system": "https://dmd.nhs.uk",
            "code": "4898311000001108",
            "display": "Sodium chloride 0.9% infusion 100ml bags"
          }
        ]
      }
    }
  ]
}
```

Where a diluent volume is required that does not align with VMP pack sizes then you can use a VTM and specify the strength and volume within the `strength` element.

For example, I want to specify a diluent of **75 mL of Sodium chloride 0.9%**. 

```json
{
  "resource": {
    "resourceType": "Medication",
    "id": "aa3d3b67-e390-4b67-98ea-f7a04533f727",
    "meta": {
      "profile": [
        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication"
      ]
    },
    "text": {
      "status": "generated",
      "div": "Sodium chloride 0.9% 75mL"
    }
    "code": {
      "text": "Sodium chloride 0.9% 75mL"
    },
    "amount": {
      "numerator": {
        "value": 75,
        "unit": "mL",
        "system": "http://unitsofmeasure.org",
        "code": "mL"
      },
      "denominator": {
        "value": 1
      }
    },
    "ingredient": [
      {
        "itemCodeableConcept": {
          "coding": [
            {
              "system": "https://dmd.nhs.uk",
              "code": "777553004",
              "display": "Sodium chloride"
            }
          ]
        },
        "strength": {
          "numerator": {
            "value": 0.9,
            "unit": "%",
            "system": "http://unitsofmeasure.org",
            "code": "%"
          },
          "denominator": {
            "value": 1
          }
        }
      }
    ]
  }
}
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<strong>IMPORTANT:</strong> Where a <code>Medication</code> resource is being created with two or more ingredients, there may not be a single dm+d code that represents that combined medication. UKCore has profiled the <code>code</code> element as <strong>mandatory</strong>. In this scenario use a meaningful <code>text</code> description of the combined medication. Consuming systems can choose to ignore this text description and process only the coded data. 
</div>

For example;

```json
{
  "resource": {
    "resourceType": "Medication",
    "id": "1de16152-1a0e-400f-bbe9-6be3eeb086a4",
    "meta": {
      "profile": [
        "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication"
      ]
    },
    "form": {
      "coding": [
        {
          "system": "http://snomed.info/sct",
          "code": "385229008",
          "display": "Solution for infusion"
        }
      ]
    },
    "code": {
      "text": "20ml Calcium Gluconate 10% in 75 ml Glucose 5% solution for infusion"
    },
    "ingredient": [
      {
        "isActive": "true",
        "itemCodeableConcept": {
          "coding": [
            {
              "system": "https://dmd.nhs.uk",
              "code": "775002009",
              "display": "Calcium gluconate"
            }
          ]
        },
        "strength": {
          "numerator": {
            "value": 10,
            "unit": "percent",
            "system": "http://unitsofmeasure.org",
            "code": "%"
          },
          "denominator": {
            "value": 20,
            "unit": "millilitre",
            "system": "http://unitsofmeasure.org",
            "code": "mL"
          }
        }
      },
      {
        "itemCodeableConcept": {
          "coding": [
            {
              "system": "https://dmd.nhs.uk",
              "code": "776119003",
              "display": "Glucose"
            }
          ]
        },
        "strength": {
          "numerator": {
            "value": 5,
            "unit": "percent",
            "system": "http://unitsofmeasure.org",
            "code": "%"
          },
          "denominator": {
            "value": 75,
            "unit": "millilitre",
            "system": "http://unitsofmeasure.org",
            "code": "mL"
          }
        }
      }
    ]
  }
}
```

## Reconstituting Liquid

It is not common practice for a prescriber to specify the reconstituting liquid used to prepare the active ingredient, usually in powder form, for injection into an infusion bag.

Unless required for specific clinical reasons, **DO NOT** specify the reconstituting liquid within the FHIR `MedicationRequest`.

In the majority of cases, the clinical staff will determine what is the most appropriate reconstituting liquid, and the required volume of liquid for the prescribed volume/strength of the active ingredient.

Where a reconstituting liquid is required to be specified, it could be defined as an `ingredient` within a referenced `Medication` resource of the `MedicationRequest`. For example;

```json
{
  "ingredient": [
    {
      "itemCodeableConcept": {
        "coding": [
          {
            "system": "https://dmd.nhs.uk",
            "code": "39720011000001104",
            "display": "Water for injections 20ml ampoules"
          }
        ]
      }
    }
  ]
}
```

There is no way in FHIR to state the above is for reconstituting purposes, so this would have to be assumed by the clinician.

For the most complex edge case when all of the above needs to be specified by the prescriber; the active ingredient, diluent and reconstituting liquid, the FHIR standard can convey the data, but cannot describe the method for preparing the infusion.

In the example below, the infusion ingredients are;

**Co-amoxiclav 1.2 gram** reconstituted with a **Water for injections 20ml ampoule** then injected into a **Sodium chloride 0.9% infusion 100ml bag**

Note that this example is only a fragment and does not include all required business data for a `MedicationRequest` referencing a `Medication` within a `Bundle`.

```json
{
  "resourceType": "Bundle",
  "entry": [
    {
      "resource": {
        "resourceType": "Medication",
        "id": "11dc9519-b6e8-41bb-bce5-f6f724b743bc",
        "form": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "385229008",
              "display": "Solution for infusion"
            }
          ]
        },
        "code": {
          "text": "Co-amoxiclav 1.2 gram reconstituted with Water for injections 20ml ampoules in Sodium chloride 0.9% infusion 100ml bags"
        },
        "ingredient": [
          {
            "itemCodeableConcept": {
              "coding": [
                {
                  "system": "https://dmd.nhs.uk",
                  "code": "774587000",
                  "display": "Co-amoxiclav"
                }
              ]
            },
            "strength": {
              "numerator": {
                "value": 1.2,
                "unit": "gram",
                "system": "http://unitsofmeasure.org",
                "code": "g"
              },
              "denominator": {
                "value": 1
              }
            }
          },
          {
            "itemCodeableConcept": {
              "coding": [
                {
                  "system": "https://dmd.nhs.uk",
                  "code": "4898311000001108",
                  "display": "Sodium chloride 0.9% infusion 100ml bags"
                }
              ]
            }
          },
          {
            "itemCodeableConcept": {
              "coding": [
                {
                  "system": "https://dmd.nhs.uk",
                  "code": "39720011000001104",
                  "display": "Water for injections 20ml ampoules"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "resourceType": "MedicationRequest",
      "id": "34eb3c92-76e6-48c2-9691-aa1f0b58369b",
      "medicationReference": {
        "reference": "11dc9519-b6e8-41bb-bce5-f6f724b743bc",
        "type": "Medication"
      }
    }
  ]
}
```

The above example is an extreme edge case that is likely not required for a minimum viable product for a clinical solution that supports infusions using the FHIR standard.
<!--
## Using Mutliple Medication Resources

to be written
-->
---
