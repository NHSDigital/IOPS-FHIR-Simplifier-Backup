## Translation Process

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
      <strong>Important:</strong> The process described here is to create a suitable short list of products to fulfil the medication request
</div>

It is not intended to identify a single product. A local implementation may choose to further filter the list of products on factors like local availability (stock), local formulary or cost. The order of products listed may also be locally condfigured to promote or demote products based on licensing status or local needs such as paediatric use.

The translation process requires the use of the NHS Dictionary of Medicines and Devices (dm+d) plus a mapping table for UCUM units of measure that use different terms than dm+d. 

For example; `gram` is a dm+d unit of measure with `g` is the equivalant within UCUM, and UCUM spells `liter` differently to the dm+d `litre`.

### Step #1: Get child VMPs of the VTM

VMP’s flagged within dm+d as invalid or where actual products are not available must be ignored.

Where the dose-based instruction specifies a coded Route or coded Form then these are used in the query to return only VMPs for the given route and/or form.

In pseudo-code;

```sql
return vmp's
  where parent_vtm = {vtm_id}
    and vmp is valid
      and vmp has actual products available
       and vmp_form = {form_id} (if specified)
        and vmp_route = {route_id}  (if specified)
```

### Step #2: Calculate the required quantity of each VMP to fulfil the requested dose

Take the dose from the `doseAndRate.doseQuantity` or `doseAndRate.doseRange.low` structures. This will be a combination of a quantity and a coded unit of measure. If the unit of measure is using a UCUM unit then the SNOMED code needs to be looked-up from dm+d. This is where the addition mapping table applies.

Each VMP contains strength information for the active ingredients. It would not be expected to use a dose-based prescription for combination drugs (e.g. anything beginning “co-“) nor any VTM where some associated products contained multiple ingredents (e.g. Phosphate). In such cases translation from dose to products is not possible.

The strength of the ingredient may need to be converted into the same units as the requested dose for comparision purposes. For example, if the requested dose is 1gram but the VMP ingredient is expressed as 500mg then it would need to be converted into 0.5gram to calculate that the VMP is half the required strength. Whilst most dosage instructions would be expressed in terms of strength, the same conversion is required for volume (litre, millitre etc.) and length (metre, centimetre, etc.).

With all units of measure expressed in the same scaler terms, the amount of the VMP to fulfil the requested dose can be calculated as; 

`QUANTITY OF VMP = ( REQUESTED DOSE QUANTITY / VMP INGREDIENT STRENGTH ) / VMP UNIT DOSE FORM STRENGTH (where defined for the VMP)`

**Worked Example**

Requested dose-based instruction = **Oxytetracycline** with a DOSE of 250 milligram

<table data-responsive>
<thead>
<tr>
<th>Product (VMP)</th>
<th>Quantity Calculation</th>
<th>Unit of Measure</th>
</tr>
</thead>
<tbody>
<tr>
<td>Oxytetracycline 100mg/5ml oral suspension</td>
<td><code>250 / (20/1) = 12.5</code></td>
<td>ml</td>
</tr>
<tr>
<td>Oxytetracycline 125mg/5ml oral suspension</td>
<td><code>250 / (25/1) = 10</code></td>
<td>ml</td>
</tr>
<tr>
<td>Oxytetracycline 250mg tablets</td>
<td><code>250 / (250) = 1</code></td>
<td>tablet</td>
</tr>
<tr>
<td>Oxytetracycline 250mg/5ml oral suspension</td>
<td><code>250 / (50) = 5</code></td>
<td>ml</td>
</tr>
<tr>
<td>Oxytetracycline 500mg/5ml oral suspension</td>
<td><code>250 / (100/1) = 2.5</code></td>
<td>ml</td>
</tr>
</tbody>
</table>

**Note**. The VMP `Oxytetracycline 250mg tablets` has a Unit Dose Form Strength (UDFS) defined of "1 tablet"

### Step #3 - Order the list of VMPs in a clinically suitable order

This approach **does not** include where two or more products of different strengths may be used. For example a dose of 75mg requested and fulfilled by one 50mg product and one 25mg product.

This guidance suggests ordering by least divisibility.

1. Whole products that can fulfil the request are listed above products that may have to be divided.

2. Where the quantity calculated from Step 2 is not divisible by 1, hence the product has to be divided (e.g. 1.5 tablets) then push down the list.

3. Where the quantity calculated from Step 2 is less than 1 (e.g. 0.5 tablets) then push lower in the list.

4. In either case, when a product needs to be divided and if the product has a dose form that is not typically divisable then push even lower in the list.

5. Products containing multiple active ingredents are pushed to the bottom of the list as the translation calculatation is not possible.

Using the above example, the resulting sort order would be;

<table data-responsive>
<thead>
<tr>
<th>Product (VMP)</th>
<th>Quantity (to fulfil 250 milligrams)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Oxytetracycline 250mg tablets</td>
<td>1 tablet</td>
</tr>
<tr>
<td>Oxytetracycline 250mg/5ml oral suspension</td>
<td>5 ml</td>
</tr>
<tr>
<td>Oxytetracycline 125mg/5ml oral suspension</td>
<td>10 ml</td>
</tr>
<tr>
<td>Oxytetracycline 500mg/5ml oral suspension</td>
<td>2.5 ml</td>
</tr>
<tr>
<td>Oxytetracycline 100mg/5ml oral suspension</td>
<td>12.5 ml</td>
</tr>
</tbody>
</table>

---