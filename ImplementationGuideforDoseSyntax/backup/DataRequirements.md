## Data Requirements

## dm+d

The dm+d data fields used for this process are;

<table data-responsive>
<thead>
<tr>
<th data-no-sort>VTM</th>
<th data-no-sort>VMP</th>
<th data-no-sort>VMP-VPI</th>
<th data-no-sort>VMP-FORM</th>
<th data-no-sort>VMP-ROUTE</th>
</tr>
</thead>
<tbody>
<tr>
<td>VTMID</td>
<td>VTMID</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td>VPID</td>
<td>VPID</td>
<td>VPID</td>
<td>VPID</td>
</tr>
<tr>
<td>NM</td>
<td>NM</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>INVALID</td>
<td>INVALID</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td>NON_AVAILCD</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td>UDFS</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td>UDFS_UOMCD</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td>UNIT_DOSE_UOMCD</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td>STRNT_NMRTR_VAL</td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td>STRNT_NMRTR_UOMCD</td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td>STRNT_DNMTR_VAL</td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td>STRNT_DNMTR_UOMCD</td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td>FORMCD</td>
<td>ROUTECD</td>
</tr>
</tbody>
</table>

Together with the FORM, ROUTE and UNIT_OF_MEASURE vocabularies from the dm+d **LOOKUP** data.

When dm+d data is imported into a relational database, concepts marked as INVALID or VMP concepts flagged as "not actual products available" may be excluded from the import.

{{render: logical-dmd-erd}}{: .img-responsive .centered }

### Mapping between UCUM and SNOMED/dm+d

The following mapping table needs to be available to the implementing system. It is required to identify the units of measure within the UCUM standard that use different different codes to the dm+d.

For example `g` is a UCUM code for "gram" and the equivalent within dm+d is `gram|258682000` so a mapping is required to associate `g` with the SNOMED code `258682000`. This mapping table may need to be extended within a local implementation depending on which UCUM units are to be expected.

<table data-responsive>
<thead>
<tr>
<th>SNOMED/dm+d code</th>
<th>UCUM unit</th>
</tr>
</thead>
<tbody>
<tr>
<td>258683005</td>
<td>kilogram</td>
</tr>
<tr>
<td>258682000</td>
<td>g</td>
</tr>
<tr>
<td>258684004</td>
<td>milligram</td>
</tr>
<tr>
<td>258686002</td>
<td>ng</td>
</tr>
<tr>
<td>258685003</td>
<td>ug</td>
</tr>
<tr>
<td>258773002</td>
<td>milliliter</td>
</tr>
<tr>
<td>258770004</td>
<td>liter</td>
</tr>
<tr>
<td>258770004</td>
<td>l</td>
</tr>
</tbody>
</table>

---