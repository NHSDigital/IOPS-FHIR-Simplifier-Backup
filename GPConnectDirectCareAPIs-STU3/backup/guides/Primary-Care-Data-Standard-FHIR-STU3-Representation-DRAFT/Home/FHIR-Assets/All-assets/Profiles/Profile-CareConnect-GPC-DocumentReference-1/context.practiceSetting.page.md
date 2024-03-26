## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Additional details about where the content was created (for example, clinical specialty), the value **SHOULD** be taken from the refset. Other classifications of documents should be sent as text.

<h5><ins>Example</ins></h5>

```xml
<context>
    <practiceSetting>
        <coding>
            <display value="General practice service" />
            <code value="1060971000000108" />
            <system value="http://snomed.info/sct" />
        </coding>
    </practiceSetting>
</context>
```

---