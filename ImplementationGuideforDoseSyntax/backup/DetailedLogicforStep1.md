## Step 1 - Get child VMPs of the VTM

A suitable SQL query to return child VMPs for a VTM, with optional Route or Form constraints would be as follows. This assumes INVALID concepts and VMPs where no actual products are available has been excluded from the database.

```sql
SELECT vmp.vmpid AS vmpId
     , vmp.name AS vmpName
     , vmp.udfs_dose_uomcd AS unitDoseFormStrength
     , vpi.strnt_dnmtr_uomcd AS denominator
  FROM vtm
 INNER JOIN vmp 
    ON ( vtm.vtmid = vmp.vtmid )
 INNER JOIN vmpform 
    ON ( vmp.vmpid = vmpform.vmpid )
 INNER JOIN vmproute 
    ON ( vmp.vmpid = vmproute.vmpid )
 INNER JOIN vpi 
    ON ( vmp.vmpid = vpi.vmpid )
 WHERE vtm.vtmid = {insert_vtm_id}
   AND ( vmpform.formid = IN_form_id OR ISNULL(IN_form_id) )
   AND ( vmproute.routeid = IN_route_id OR ISNULL(IN_route_id) )
```

---