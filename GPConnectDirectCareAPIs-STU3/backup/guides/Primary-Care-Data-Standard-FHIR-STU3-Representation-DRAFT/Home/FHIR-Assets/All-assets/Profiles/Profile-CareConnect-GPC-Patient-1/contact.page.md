## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The `Patient.contact` element **SHALL** be populated where demographic information is available in the Patient record for those individuals who may need to be contacted in connection with the Patient’s appointment. In accordance with the FHIR definition, it is "Not applicable to register pedigree and family ties beyond use of having contact".

- `relationship.text` **SHALL** be populated with the type of relationship, for example _Emergency contact_, _Next of kin_, or _Carer_. The element **SHALL** also be used where a family relationship is recorded, for example _Daughter_. Multiple relationship entries are allowed.
- `relationship.coding` **SHALL NOT** be populated
- `name`, `telecom`, `address`, `gender`, `organization` and `period` **SHALL** be populated where data is available
- `address` and `telecom` **SHALL** follow the Address and ContactPoint rules above for population of these elements

<h5><ins>Example</ins></h5>

```xml
<contact>
    <relationship>
        <text value="Emergency contact" />
        <text value="Next of kin" />
        <text value="Daughter" />
    </relationship>
    <name>
        <use value="official"/>
        <text value="JACKSON Jane (Miss)"/>
        <family value="Jackson" />
        <given value="Jane"/>
        <prefix value="Miss"/>
    </name>
    <telecom>
        <system value="phone"/> 
        <value value="07777123123"/> 
        <use value="mobile" />
    </telecom>
    <address>
        <use value="home"/>
        <type value="physcial"/>
        <line value="Trevelyan Square, Boar Ln"/>
        <city value="Leeds"/>
        <district value="West Yorkshire"/>
        <postalCode value="LS1 6AE"/>
    </address>
    <gender value="female"/>
    <period>
        <start value="2012"/>
    </period>
</contact>
```

---