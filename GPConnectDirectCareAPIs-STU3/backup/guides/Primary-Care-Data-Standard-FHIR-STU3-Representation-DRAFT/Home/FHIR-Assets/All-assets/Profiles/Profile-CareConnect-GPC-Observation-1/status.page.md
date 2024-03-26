## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

### Test Group Header

The status of the test group header.

In GP systems, these are most likely to be `final`. However, `preliminary` reports are possible as, for example, some work can be sub-contracted to other labs. If the system is not able to determine the status of a test group header then it should default to the `unknown` value.

### Individual Test Result

The status of the test result.

In GP systems, these are most likely to be `final`. However, `preliminary` reports are possible as, for example, some work can be sub-contracted to other labs. If the system is not able to determine the status of a test group header then it should default to the `unknown` value.

### Filing Comments

For filing comments this is a set value of `unknown`.

### Observations including Blood Pressure

Fixed value of `final`.

The code system for this status can be found using the link below:

<i class="fa fa-link"></i> [http://hl7.org/fhir/observation-status](http://hl7.org/fhir/observation-status)

<h5><ins>Example</ins></h5>

```xml
<status value="final" />
```

---