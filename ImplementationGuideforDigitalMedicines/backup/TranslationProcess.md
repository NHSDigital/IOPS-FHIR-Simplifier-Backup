## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
      <strong>Important:</strong> The process described here is to create a suitable short list of products to fulfil the medication request
</div>

It is not intended to identify a single product. A local implementation may choose to further filter the list of products on factors like local availability (stock), local formulary or cost. The order of products listed may also be locally condfigured to promote or demote products based on licensing status or local needs such as paediatric use.

The translation process requires the use of the NHS Dictionary of Medicines and Devices (dm+d) plus a mapping table for UCUM units of measure that use different terms than dm+d. 

For example; `gram` is a dm+d unit of measure with `g` is the equivalant within UCUM, and UCUM spells `liter` differently to the dm+d `litre`.

### Step #1: Get valid to prescribe child products (VMPs and AMPs) of the VTM

The `Prescribing Status` flag is held at the VMP level. The dm+d (as of February 2025) has four values for this flag.
 
1 = Valid as a prescribable product

2 = Invalid to prescribe in NHS primary care

4 = Never Valid To Prescribe As A VMP

9 = Caution - AMP level prescribing advised

If using dm+d data held in a relational database, the pseudo-SQL would be;

```sql
return vmp, vmp_prescribing_status
  where parent_vtm = {vtm_id}
    and vmp is valid
      and vmp has actual products available
        and vmp has vmp_prescribing_status = 0001
          and vmp_form = {form_id} (if specified)
            and vmp_route = {route_id}  (if specified)
```
```sql
return amp, vmp, vmp_prescribing_status
  where parent_vtm = {vtm_id}
    and vmp is valid
      and vmp has actual products available
        and vmp has vmp_prescribing_status = 0004 or 0009
          and vmp_form = {form_id} (if specified)
            and vmp_route = {route_id}  (if specified)
              and parent_vmp = vmp
```

If using the [NHS England Terminology Server](https://digital.nhs.uk/services/terminology-servers) then a two-step approach is required. First a call to return VMP concepts for the given VTM with optional Form and Route codes. Second, for any VMPs flagged to prescribe with an AMP, those flagged with a PRES_STATCD of 0004 or 0009, make an additional call to return AMPs.

To return VMPs;

```json
curl --location 'https://ontology.nhs.uk/production1/fhir/ValueSet/$expand' \
--header 'Authorization: Bearer } { { OAuthToken } }' \
--header 'Content-Type: application/json' \
--data '{
"resourceType": "Parameters",
"parameter": [
  {
  "name": "valueSet",
    "resource": {
      "resourceType": "ValueSet",
      "compose": {
        "include": [
          {
          "system": "https://dmd.nhs.uk",
          "filter": [
            {
            "property": "parent",
            "op": "=",
            "value": "{vtm_id}"
            },
            {
            "property": "parent",
            "op": "=",
            "value": "VMP"
            },
            {
            "property": "INVALID",
            "op": "exists",
            "value": "false"
            },
            {
            "property": "FORMCD",
            "op": "in",
            "value": "{form1_id},{form2_id}"
            },
            {
            "property": "ROUTECD",
            "op": "=",
            "value": "{route_id}"
            }
          ]
          }
        ],
        "exclude": [
        {
          "system": "https://dmd.nhs.uk",
          "filter": [ 
          {
          "property": "NON_AVAILCD",
          "op": "=",
          "value": "1"
          }
          ]
        }
        ]
      }
    }
  }
]
}'
```

To return AMPs;

```json
curl --location 'https://ontology.nhs.uk/production1/fhir/ValueSet/$expand' \
--header 'Authorization: Bearer { { OAuthToken } }' \
--header 'Content-Type: application/json' \
--data '{
"resourceType": "Parameters",
"parameter": [
{
  "name": "valueSet",
  "resource": {
    "resourceType": "ValueSet",
    "compose": {
      "include": [
        {
        "system": "https://dmd.nhs.uk",
        "filter": [
          {
          "property": "parent",
          "op": "in",
          "value": "{vpm1_id},{vpm2_id},{vpm3_id}"
          },
          {
          "property": "parent",
          "op": "=",
          "value": "AMP"
          },
          {
          "property": "INVALID",
          "op": "exists",
          "value": "false"
          }
          ]
        }
        ],
        "exclude": [
          {
          "system": "https://dmd.nhs.uk",
          "filter": [
          {
          "property": "AVAIL_RESTRICTCD",
          "op": "in",
          "value": "9"
          }
          ]
          }
        ]
      }
    }
  }
]
}'
```

### Step #2: Calculate the required quantity of each VMP to fulfil the requested dose

Take the dose from the `doseAndRate.doseQuantity` or `doseAndRate.doseRange.low` structures. This will be a combination of a quantity and a coded unit of measure. If the unit of measure is using a UCUM unit then the SNOMED code needs to be looked-up from dm+d. This is where the addition mapping table applies.

This calculation at the VMP level will apply to all child AMPs.

Each VMP contains strength information for the active ingredients. It would not be expected to use a dose-based prescription for combination drugs (e.g. anything beginning “co-“) nor any VTM where some associated products contained multiple ingredents (e.g. Phosphate). In such cases translation from dose to products is not possible.

The strength of the ingredient may need to be converted into the same units as the requested dose for comparision purposes. For example, if the requested dose is 1gram but the VMP ingredient is expressed as 500mg then it would need to be converted into 0.5gram to calculate that the VMP is half the required strength. Whilst most dosage instructions would be expressed in terms of strength, the same conversion is required for volume (litre, millitre etc.) and length (metre, centimetre, etc.).

With all units of measure expressed in the same scaler terms, the amount of the VMP to fulfil the requested dose can be calculated as; 

`QUANTITY OF VMP = ( REQUESTED DOSE QUANTITY / VMP INGREDIENT STRENGTH ) / VMP UNIT DOSE FORM STRENGTH (where defined for the VMP)`

### Step #3 - Order the list of products in a clinically suitable order

This approach **does not** include where two or more products of different strengths may be used. For example a dose of 75mg requested and fulfilled by one 50mg product and one 25mg product.

Exclude VMPs flagged as `Never valid to prescribe as a VMP`.

This guidance suggests ordering by least divisibility.

1. Whole products that can fulfil the request are listed above products that may have to be divided.

2. Where the quantity calculated from Step 2 is not divisible by 1, hence the product has to be divided (e.g. 1.5 tablets) then push down the list.

3. Where the quantity calculated from Step 2 is less than 1 (e.g. 0.5 tablets) then push lower in the list.

4. In either case, when a product needs to be divided and if the product has a dose form that is not typically divisable then push even lower in the list.

5. Products containing multiple active ingredents are pushed to the bottom of the list as the translation calculatation is not possible.

---