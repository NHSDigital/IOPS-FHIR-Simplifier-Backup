## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

- Where the consultation record has been finalised on the provider system set the value of this element to `finished`.
- Where the consultation record has been saved onto the provider system in a draft (or equivalent) status, then set value of this element to `unknown`.

Existing vocabulary is driven by use of Encounter for appointment style encounters rather than provision of consultation context. Hence, use the most appropriate value from limited set available.

<i class="fa fa-link"></i> [http://hl7.org/fhir/encounter-status](http://hl7.org/fhir/encounter-status)

<h5><ins>Example</ins></h5>

```xml
<status value="finished" />
```

---