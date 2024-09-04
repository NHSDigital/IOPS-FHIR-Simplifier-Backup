## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A device that is implanted, removed or otherwise manipulated (calibration, battery replacement, fitting a prosthesis, attaching a wound-vac, etc.) as a focal portion of the Procedure.

<h5><ins>Example</ins></h5>

```xml

  <focalDevice> 
    <action> 
      <coding> 
        <system value="http://hl7.org/fhir/device-action"/> 
        <code value="implanted"/> 
      </coding> 
    </action> 
    <manipulated> 
      <reference value="Device/example-pacemaker"/> 
    </manipulated> 
  </focalDevice> 
  ```
  ---