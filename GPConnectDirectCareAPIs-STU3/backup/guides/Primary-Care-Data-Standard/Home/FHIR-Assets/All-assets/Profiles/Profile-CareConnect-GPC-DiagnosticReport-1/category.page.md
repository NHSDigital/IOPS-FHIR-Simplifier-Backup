## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The general type of test report. 

A default value of `LAB` (Laboratory) should be used if a more specific value is not available - for example, pathology, or microbiology.


<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Consuming systems need to be aware that where more detailed categories are provided the categorisation may vary. How laboratories categorise in the UK is not consistent, and this needs to be taken into account if any type of filtering is being considered.
</div>

<h5><ins>Example</ins></h5>

```xml
<category>
    <coding>
      <system value="http://snomed.info/sct"/>
      <display value="Pathology"/>
      <code value="39459002"/>
    </coding>
</category>
```

---