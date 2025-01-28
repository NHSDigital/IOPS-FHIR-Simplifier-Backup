## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

Who created the task. This element can include references to other resources to show both the requester.agent (this could be a patient, practitioner, organization etc) and requester.onBehalfOf (the organization) but only the requester.agent is mandatory

<h5><ins>Example</ins></h5>

```xml
<requester> 
    <agent> 
      <reference value="Practitioner/example"/> 
      <display value="Dr Adam Careful"/> 
    </agent> 
    <onBehalfOf> 
      <reference value="Organization/2.16.840.1.113883.19.5"/> 
      <display value="Good Health Clinic"/>
    </onBehalfOf> 
  </requester> 
```

---