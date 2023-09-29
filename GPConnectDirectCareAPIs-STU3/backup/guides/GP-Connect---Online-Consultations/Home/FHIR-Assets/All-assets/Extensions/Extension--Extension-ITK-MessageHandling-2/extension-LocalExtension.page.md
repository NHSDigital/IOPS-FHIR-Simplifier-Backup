## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `LocalExtension` element **MUST** be populated with a string, identifiying the type of document which you are sending. The recipient will use this value to determine how to act on the information.

The current (known) values in use for the capability are below:

- `SendDocument-ConsultationReport` (Consultation Summary Report)



<h5><ins>Example</ins></h5>

```xml
<!-- LocalExtension - Conveys the identifier of the GP Connect Send Document health or social care use case -->
<extension url="LocalExtension">
    <valueString value="SendDocument-<Foo><Bar>" />
</extension>
```

---