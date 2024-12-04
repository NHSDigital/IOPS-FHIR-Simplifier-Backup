## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<b>Sender</b>

The `ITK-MessageHeader-2.event` **MUST** contain a fixed value of `ITK009D` (ITK Digital Medicine Immunization Document) from the code system [ITK-MessageEvent-2](https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2).

<b>ITK3 responses generated</b>

The `event` **MUST** contain a fixed value of `ITK008M` from the code system [ITK-MessageEvent-2](https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2).


<h5><ins>Example</ins></h5>

```xml
<event>
   <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2"/>
   <code value="ITK009D"/>
   <display value="ITK Digital Medicine Immunization Document"/>
</event>
```
---