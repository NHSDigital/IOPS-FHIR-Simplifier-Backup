## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `status` element is a mandatory one within FHIR and while it can be populated with any value from the available code system, it is expected that must use-cases within GP Connect will be `order`.

<i class="fa fa-link"></i> [Code System Request Intent](http://hl7.org/fhir/R4B/valueset-request-intent.html)

<h5><ins>Example</ins></h5>

```xml
<status value="order" />
```

---