## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

The fullUrl for the resource, this **MUST** be an absolute URL. The URL will not resolve in the case of resources that don’t have a read endpoint, for example, `Practitioner`. These non-resolvable URLs are used to assist consumers in resolving references within Bundle resources.

<h5><ins>Example</ins></h5>

```xml
<entry>
    <fullUrl value="Device/56C7021B-6587-49C7-AD18-6781F8FDE2C1" />
</entry>
```

---