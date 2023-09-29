## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<b>Senders</b>

The `SenderReference` element **MUST** be set to the unique identifier of the activity which has taken place at the sender organisation.


<b>ITK3 responses generated</b>

The `SenderReference` element **MUST** contain the same value as the sender provided.

<h5><ins>Example</ins></h5>

```xml
<!-- Sender Reference - unique identifier of activity -->
<extension>
    <url value="SenderReference" />
    <valueString value="846ebe66-5ff8-4499-bc57-a112d3d0daa3" />
</extension>
```

---