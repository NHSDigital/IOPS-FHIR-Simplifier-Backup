## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>
	
Identifies a planned action to occur as part of the plan. For example, a medication to be used, lab tests to perform, self-monitoring, education, etc.

<h5><ins>Example</ins></h5>

```xml
 <activity> 
    <outcomeCodeableConcept> 
      <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="161832001"/> 
        <display value="Progressive weight loss"/> 
      </coding> 
    </outcomeCodeableConcept> 
    <outcomeReference> 
      <reference value="Observation/example"/> 
      <display value="Weight Measured"/> 
    </outcomeReference>
    <status value="completed"/> 
    <statusReason value="Achieved weight loss to mitigate diabetes risk."/> 
  </activity> 
```

---