## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle avoid" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `LocalExtension` element **MUST** be populated with `None`.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note to receivers (consumers)</b>: <code>v1.x.x</code> of the GP Connect Send Document specification used to require that this element be populated. Please disregard this value and <b>MUST NOT</b> be use for the purpose of identifying the type of document which has been sent.
</div>

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="LocalExtension" />
    <valueString value="SendDocument-ConsultationReport" />
</extension>
```

---