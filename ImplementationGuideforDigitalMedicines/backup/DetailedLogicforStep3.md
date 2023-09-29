## {{page-title}} - Order the list of products in a clinically suitable order

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
TO DO. These stored procedures need to be extended to show relevant AMPs and hide VMPs flagged as <code>Never valid to prescribe as a VMP</code>.
</div>

### Function for ranking / ordering

Uses the `FNC_CALC_QTY` function from above then calculates a ranking value which can be used to order the overall SQL query.

```sql
FUNCTION FNC_CALC_RANK( doseQty DECIMAL(9,3)
                      , numerator DECIMAL(30,12)
                      , denominator DECIMAL(9,3)
                      , unitDoseFormStrength DECIMAL
                      , formId BIGINT UNSIGNED
                      )
RETURNS SMALLINT(5) UNSIGNED

BEGIN
	DECLARE v_qty DECIMAL(30,12) UNSIGNED;
	DECLARE v_rank SMALLINT UNSIGNED;
	DECLARE v_divisable BIGINT UNSIGNED;

	SET v_qty = FNC_CALC_QTY(doseQty, numerator, denominator, unitDoseFormStrength);

	IF ( v_qty < 1 ) 
            THEN SET v_rank = 3;
	ELSE IF ( ( v_qty % 1 ) != 0 )
            THEN  SET v_rank = 2;
	ELSE 
	   SET v_rank = 1;
	END IF;

	IF ( v_rank != 1 )
            THEN SELECT name
                   FROM lookup
                  WHERE valueset = "NOTDIVISABLE"
                    AND id = formid 
                   INTO v_divisable;
	
            IF ( NOT NULL(v_divisable) ) 
                THEN SET v_rank = 4; 
            END IF;
	END IF;

	RETURN v_rank;
END
```

Where `formid` is the dm+d code for the requested dose quantity unit of measure.

The rules for the ranking are best shown in a table.

| Calculated Quantity                               | Ranking | Ranking Reason                                      |
| ------------------------------------------------- | ------- | --------------------------------------------------- |
| Integer                                           | 1       | Can be fulfilled by one or more complete doses      |
| Decimal greater than 1                            | 2       | Requires a number of doses include part doses       |
| Decimal less than 1                               | 3       | Requires part of a a single dose                    |
| Decimal using a dose form typically not divisable | 4       | Unlikely to the clinically safe to use this product |

<br/>

### Identification of dose forms that are typically not divisable

The following dose forms are typically not divisible, however this is not always the case.

For example there are some modified-release tablets with a score along the centre to aid division, but in most cases, modified-release products should not be divided. 

The same applies for products as capsules. These represent the more common dose forms used within dm+d concepts. Other non-divisible dose forms may exist but their use would be rare, but this reference table can be extended or customised as required for a local implementation.


| SNOMED / dm+d code | Dose Form                |
| ------------------ | ------------------------ |
| 385049006          | Capsule                  |
| 385054002          | Modified-release capsule |
| 385061003          | Modified-release tablet  |
| 421720008          | Spray                    |

<br/>

### Complete Stored Procedure

```sql
PROCEDURE PRC_VTM_TO_VMP( IN IN_vtm_id BIGINT UNSIGNED
                        , IN IN_dose_qty DECIMAL
                        , IN IN_dose_uom_cd BIGINT UNSIGNED
                        , IN IN_form_id BIGINT UNSIGNED
                        , IN IN_route_id BIGINT UNSIGNED
                        )
BEGIN
	SELECT DISTINCT vmp.vmpid
        , vmp.name
        , FNC_CALC_QTY( IN_dose_qty
                      , FNC_CONVERT_UNITS( vpi.strnt_nmrtr_val
                                         , vpi.strnt_nmrtr_uomcd
                                         , IN_dose_uom_cd
                                         )
                      , vpi.strnt_dnmtr_val,vmp.udfs
                      ) AS qty
        , vmp.udfs_dose_uomcd
        , vpi.strnt_dnmtr_uomcd
        , FNC_CALC_RANK( IN_dose_qty
                       , FNC_CONVERT_UNITS( vpi.strnt_nmrtr_val
                                          , vpi.strnt_nmrtr_uomcd
                                          , IN_dose_uom_cd
                                          )
                       , vpi.strnt_dnmtr_val
                       , vmp.udfs,vmpform.formid
                       ) AS rnk
	  FROM vtm 
	 INNER JOIN vmp 
       ON ( vtm.vtmid = vmp.vtmid )
	 INNER JOIN vmpform
       ON ( vmp.vmpid = vmpform.vmpid )
	 INNER JOIN vmproute
       ON ( vmp.vmpid = vmproute.vmpid )
	 INNER JOIN vpi
       ON ( vmp.vmpid = vpi.vmpid )
	 INNER JOIN lookup
       ON ( vpi.strnt_nmrtr_uomcd = lookup.id )
	 WHERE vtm.vtmid = IN_vtm_id
	   AND ( vmpform.formid = IN_form_id OR ISNULL(IN_form_id) )
	   AND ( vmproute.routeid = IN_route_id OR ISNULL(IN_route_id) )
	 ORDER BY rnk ASC, qty ASC;
END
```

---