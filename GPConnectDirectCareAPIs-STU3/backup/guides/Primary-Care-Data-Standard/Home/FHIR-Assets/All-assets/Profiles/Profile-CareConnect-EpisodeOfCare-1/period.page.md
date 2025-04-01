## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `period` element is a required element which means it **MUST** be populated with values when they are known to the provider system.

- The `period.start` represents the date and time when the consultation started.
- The `period.end` reperesents the date when populated and the duration is known.

<h5><ins>Example</ins></h5>

```xml
<period>
    <start value="2022-10-28T13:38:00+00:00" />
    <end value="2022-10-28T13:53:00+00:00" />
</period>
```

---