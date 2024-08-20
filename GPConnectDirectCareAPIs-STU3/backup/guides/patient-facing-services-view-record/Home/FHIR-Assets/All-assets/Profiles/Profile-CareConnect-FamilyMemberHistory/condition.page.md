## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `date` element should contain the date the family history was taken.

---
<h5><ins>Example</ins></h5>

```xml

  <condition> 
    <code> 
      <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="22298006"/> 
        <display value="Myocardial Infarction"/> 
      </coding> 
      <text value="Heart Attack"/> 
    </code> 
    <contributedToDeath value="true"/> 
    <onsetAge> 
      <value value="74"/> 
      <unit value="yr"/> 
      <system value="http://unitsofmeasure.org"/> 
      <code value="a"/> 
    </onsetAge>
    ```

---