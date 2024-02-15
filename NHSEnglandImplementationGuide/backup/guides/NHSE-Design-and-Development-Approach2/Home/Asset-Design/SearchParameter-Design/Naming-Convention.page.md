## {{page-title}}

The NHSE search parameter name SHOULD follow an agreed format.
The name of a parameter consists of a number of name segments, and will be in the form:-
<br><br>
<samp><i>[Base][FHIRAssetName][SearchName]</i> </samp>

<br>

The segments are defined as follows:-

- **Base**: (Mandatory) - The base for a profile this will always be England. 
- **FHIRAssetName**: (Mandatory) - The name of the base FHIR Resource. such as the Extension-ExtensionName, or a Resource name
- **SearchName**: (Mandatory) - This SHOULD be the name of the element or the search criteria such s a specific value that is being searched on.


**Note:** "Mandatory" means that a segment SHALL be present. "Required" means that a segment SHOULD be present, in this case in the event of there being multiple profiles for one base resource.

The physical file name SHALL be in the format <i>[Base]-[FHIRAssetName]-[SearchName] </i> and SHALL be created in the file XML format.

---