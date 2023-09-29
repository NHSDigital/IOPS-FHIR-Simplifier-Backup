## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `ITK-MessageHeader-2.event` **MUST** contain a fixed value of `ITK007C` (ITK GP Connect Send Document) from the code system [ITK-MessageEvent-2](https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2).


<h5><ins>Example</ins></h5>

```xml
<event>
   <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2"/>
   <code value="ITK007C"/>
   <display value="ITK GP Connect Send Document"/>
</event>
```
---