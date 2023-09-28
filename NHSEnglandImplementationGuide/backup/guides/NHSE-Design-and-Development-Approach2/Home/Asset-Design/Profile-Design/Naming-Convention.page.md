## {{page-title}}

The NHSE profile name SHALL follow an agreed format.
The name of a profile consists of a number of name segments, and will be in the form:-
<br><br>
<samp><i>[Base][FHIRAssetName][Specialism]</i> </samp>

<br>

The segments are defined as follows:-

- **Base**: (Mandatory) - The base for a profile this will always be England. 
- **FHIRAssetName**: (Mandatory) - The name of the base FHIR Resource EG patient. 
- **Specialism**: (Required) - This is only used where there are derived NHSE profiles for a given base resource type.


**Note:** "Mandatory" means that a segment SHALL be present. "Required" means that a segment SHOULD be present, in this case in the event of there being multiple profiles for one base resource.

The physical file name SHALL be in the format <i>[Base]-[FHIRAssetName][Specialism]</i> and SHALL be created in the file XML format.

---
