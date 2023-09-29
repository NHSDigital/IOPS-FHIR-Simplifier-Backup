## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for populating the `derivedFrom` element within GP Connect has not been defined, as it is expected that the the `basedOn` element will suffice.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: Population of both <code>derivedFrom</code> and <code>baseOn</code> elements <b>should be avoided</b> as potentially confusing.
</div>

<h5><ins>Example</ins></h5>

```xml
<derivedFrom>
    <reference value="resource-any-11ks8f" />
</derivedFrom>
```

---