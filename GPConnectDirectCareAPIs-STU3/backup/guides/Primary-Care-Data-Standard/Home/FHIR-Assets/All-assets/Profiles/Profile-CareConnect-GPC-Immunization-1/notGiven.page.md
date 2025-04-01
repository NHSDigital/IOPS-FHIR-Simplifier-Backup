## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `status` element **MUST** contain a `boolean` value:

- `false` indicates a vaccination event which has been reported as given
- `true` indicates that a vaccination was intended; however, was not given

<h5><ins>Example</ins></h5>

```xml
<notGiven value="false" />
```

---