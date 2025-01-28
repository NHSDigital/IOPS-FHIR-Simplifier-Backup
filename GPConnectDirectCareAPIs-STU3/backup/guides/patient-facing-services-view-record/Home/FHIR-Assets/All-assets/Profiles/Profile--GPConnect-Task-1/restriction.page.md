## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Any constraints or limitations on the task, such as how many times it should occur. 

Note: Only applicable where the task.focus is a "request resource"

<h5><ins>Example</ins></h5>

```xml
  <restriction> 
    <repetitions value="1"/> 
    <period> 
      <end value="2016-11-02T09:45:05+10:00"/> 
    </period> 
  </restriction>
```

---