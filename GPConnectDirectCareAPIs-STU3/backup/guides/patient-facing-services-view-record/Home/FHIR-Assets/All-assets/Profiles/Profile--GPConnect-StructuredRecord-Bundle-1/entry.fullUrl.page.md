## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The fullUrl for the resource, this **MUST** be an absolute URL. The URL will not resolve in the case of resources that don’t have a read endpoint, for example, Practitioner. These non-resolvable URLs are used to assist consumers in resolving references within Bundle resources.

<h5><ins>Example</ins></h5>

```xml
<entry>
    <fullUrl value="https://example.com/base/MedicationRequest/3123" />
</entry>
```

---