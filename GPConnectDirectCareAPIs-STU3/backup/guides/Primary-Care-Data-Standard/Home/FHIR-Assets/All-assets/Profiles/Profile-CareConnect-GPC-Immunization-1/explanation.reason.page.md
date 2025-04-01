## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The reason why the immunization was given, for example, travel, occupation, and so on. This MUST be absent if notGiven is true.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This <strong>MUST</strong> be absent if <code>notGiven</code> has the value <code>true</code>.
</div>


<h5><ins>Example</ins></h5>

```xml
<explanation>
    <reason>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="443684005" />
            <display value="Disease outbreak" />
        </coding>
    </reason>
</explanation>
```

---