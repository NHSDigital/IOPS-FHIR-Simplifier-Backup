## Step 2 - Calculate the required quantity of each VMP to fulfil the requested dose

### Conversion between scaler units of measure, e.g. gram to milligram

A function is required to convert a VTM ingredient strength into the same units as the requested dose quantity. 

For example, if a required dose quantity is `12.5 milligram`, but a VMP for that drug is expressed with a strength in micrograms e.g. `500 microgram`, then that strength needs to be expressed in milligrams before the mathematical function can be executed. 

Thus `500 microgram` would be converted into `0.5 milligram`.

For example;

```sql
///
// Convert 500 micrograms into milligrams
// FNC_CONVERT_UNITS(vpi.strnt_nmrtr_val, vpi.strnt_nmrtr_uomcd, dose_uom_cd);
///

SELECT FNC_CONVERT_UNITS(500, 258685003, 258684004);

// returns `0.5`.
```

Within the dm+d, units of mass have the greatest range; **kilogram**, **gram**, **milligram**, **microgram** and **nanogram**. 

Due to this range, the data type used within SQL must be a `DECIMAL(30,12)`.

Conversion is required for the following units of measure.

<table>
<thead>
<tr>
<th data-no-sort>Category</th>
<th data-no-sort>Units</th>
<th data-no-sort>SNOMED Code</th>
<th data-no-sort>Scaler Conversion</th>
</tr>
</thead>
<tbody>
<tr>
<td class="nhsd-t-body">Mass</td>
<td class="nhsd-t-body">kilogram</td>
<td class="nhsd-t-body">258683005</td>
<td class="nhsd-t-body">10^3</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">gram</td>
<td class="nhsd-t-body">258682000</td>
<td class="nhsd-t-body">1</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">milligram</td>
<td class="nhsd-t-body">258684004</td>
<td class="nhsd-t-body">10^-3</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">microgram</td>
<td class="nhsd-t-body">258685003</td>
<td class="nhsd-t-body">10^-6</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">nanogram</td>
<td class="nhsd-t-body">258686002</td>
<td class="nhsd-t-body">10^-9</td>
</tr>
<tr>
<td class="nhsd-t-body">Volume</td>
<td class="nhsd-t-body">litre</td>
<td class="nhsd-t-body">258770004</td>
<td class="nhsd-t-body">1</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">millilitre</td>
<td class="nhsd-t-body">258773002</td>
<td class="nhsd-t-body">10^-3</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">microlitre</td>
<td class="nhsd-t-body">258774008</td>
<td class="nhsd-t-body">10^-6</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">nanolitre</td>
<td class="nhsd-t-body">282113003</td>
<td class="nhsd-t-body">10^-9</td>
</tr>
<tr>
<td class="nhsd-t-body">Length</td>
<td class="nhsd-t-body">metre</td>
<td class="nhsd-t-body">258669008</td>
<td class="nhsd-t-body">1</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">centimetre</td>
<td class="nhsd-t-body">258672001</td>
<td class="nhsd-t-body">10^-2</td>
</tr>
<tr>
<td class="nhsd-t-body"></td>
<td class="nhsd-t-body">millimetre</td>
<td class="nhsd-t-body">258673006</td>
<td class="nhsd-t-body">10^-3</td>
</tr>
</tbody>
</table>


### Function for quantity

A suitable SQL function to calculate the quantity of a given VMP to fulfil the requested dose quantity would be as follows.

```sql
FUNCTION FNC_CALC_QTY( doseQty DECIMAL(9,3)
                     , numerator DECIMAL(30,12)
                     , denominator DECIMAL(9,3)
                     , unitDoseFormStrength DECIMAL(9,3)
                     )
RETURNS DECIMAL(30,12)
BEGIN

    IF denominator = 0  
        THEN SET denominator = 1; 
    END IF;
    
    IF unitDoseFormStrength = 0
        THEN RETURN doseQty / ( numerator / denominator );
    END IF;
	
    RETURN ( doseQty / ( numerator / denominator ) ) / unitDoseFormStrength;

END
```



A description of each variable used in `FNC_CALC_QTY` is contained below.

<table>
<thead>
<tr>
<th>Variable</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>doseQty</code></td>
<td>the required dose quantity - e.g. 12.5</td>
</tr>
<tr>
<td><code>numerator</code></td>
<td>the VMP strength numerator, but has to be expressed in the same units as the requested dose, e.g. both in milligrams</td>
</tr>
<tr>
<td><code>denominator</code></td>
<td>the VMP strength denominator which may be <code>0</code> / <code>NULL</code> for some VMPs, so use a default value of 1</td>
</tr>
<tr>
<td><code>unitDoseFormStrength</code></td>
<td>the VMP unit dose form strength value, which may be <code>0</code> / <code>NULL</code></td>
</tr>
</tbody>
</table>

---