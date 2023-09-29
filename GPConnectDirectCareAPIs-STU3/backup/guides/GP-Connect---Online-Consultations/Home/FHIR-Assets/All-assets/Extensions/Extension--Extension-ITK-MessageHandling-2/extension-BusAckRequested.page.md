## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `BusAckRequested` element **MUST** be set to fixed value of `true`. 

This will request an ITK3 Response with a response code in the range `30001` to `30003`.

<h5><ins>Example</ins></h5>

```xml
<!-- Request Infrastructure ACK -->
<extension url="InfAckRequested">
    <valueBoolean value="true" />
</extension>
```

---