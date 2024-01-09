## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The status of the ProcedureRequest.

The status **MUST** only be `active`.

<i class="fa fa-link"></i> [Code System Request Status](http://hl7.org/fhir/R4/codesystem-request-status.html)

#### For investigations:

This is mandatory in the base FHIR resource. However, as this resource is not being used as a request but to hold data that would have been in a request submitted in a different format we have chosen to use the default value stated.

#### For diary entries

The provider **MUST** only include incomplete diary entries - that is, complete or cancelled **MUST NOT** be included.


<h5><ins>Example</ins></h5>

```xml
<status value="active" />
```

---