## {{page-title}}

<h5><ins>Guidance</ins></h5>

Can be used to reference another resource related to this observation

<i class="fa fa-link"></i> [Value Set: observation-relationshiptypes](http://hl7.org/fhir/stu3/valueset-observation-relationshiptypes.html)

<h5><ins>Example</ins></h5>

```xml
<related>
    <type value="sequel-to" />
    <target>
        <reference value="observation-9gf21a" />
    </target>
</related>
```

---