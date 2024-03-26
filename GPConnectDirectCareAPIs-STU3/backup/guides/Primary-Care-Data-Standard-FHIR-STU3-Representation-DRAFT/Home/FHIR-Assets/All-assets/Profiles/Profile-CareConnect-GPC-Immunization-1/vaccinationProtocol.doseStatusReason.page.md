## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for the `vaccinationProtocol.doseStatusReason` element within GP Connect has not been defined.

```xml
<vaccinationProtocol>
    <doseStatusReason>
        <coding>
            <system value="http://hl7.org/fhir/stu3/codesystem-vaccination-protocol-dose-status-reason" />
            <code value="explot" />
            <display value="Expired lot" />
        </coding>
    </doseStatusReason>
</vaccinationProtocol>
```