## `identifier`

The `identifier` is the most important element of a FHIR resource for interoperability. It acts as the **externally facing unique business identifier** for the resource. A key phrase from the FHIR R4 standard is;
> [for `identifier`] ...All resources that have an identifier element support searching by the identifier, so that records can be located by that method.

### Provider Systems

It is recommended that the `identifier` value is odsSiteCode, but another identifier can be used. 

### Consumer Systems

Consumer systems **MUST** consume this data.


The ODS site code for the location

**Location.identifier:odsSiteCode.use**
usual | official | temp | secondary | old (If known)
**Location.identifier:odsSiteCode.type**
This should be set to ???
**Location.identifier:odsSiteCode.system**
The url is ???
**Location.identifier:odsSiteCode.value**
The ODS site code
**Location.identifier:odsSiteCode.period**
The period for which the code is valid - May be omitted
**Location.identifier:odsSiteCode.assigner**
Implicit for ODS site codes - Should be omitted

---

