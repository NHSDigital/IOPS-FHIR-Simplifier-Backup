## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The status of the `ProcedureRequest`.

<i class="fa fa-link"></i> [Code System Request Intent](http://hl7.org/fhir/R4B/valueset-request-intent.html)

#### For investigations:

The `intent` **MUST** only be `order`.

<h5><ins>Example</ins></h5>

```xml
<intent value="order" />
```

#### For diary entries

The `intent` **MUST** only be `plan`.

<h5><ins>Example</ins></h5>

```xml
<intent value="plan" />
```

---