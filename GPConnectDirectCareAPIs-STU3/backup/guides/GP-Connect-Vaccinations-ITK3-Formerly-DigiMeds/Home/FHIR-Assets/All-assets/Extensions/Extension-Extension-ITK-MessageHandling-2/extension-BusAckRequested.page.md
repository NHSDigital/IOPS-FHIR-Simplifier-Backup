## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<b>Senders</b>

The `BusAckRequested` element **MUST** be set to fixed value of `true`. 

This will request an ITK3 Response with a response code in the range `30001` to `30003`.

<b>ITK3 responses generated</b>

The `BusAckRequested` element **MUST** contain a fixed value of `false`.


<h5><ins>Example</ins></h5>

```xml
<!-- Request Infrastructure ACK -->
<extension>
    <url value="BusAckRequested" />
    <valueBoolean value="true" />
</extension>
```

---