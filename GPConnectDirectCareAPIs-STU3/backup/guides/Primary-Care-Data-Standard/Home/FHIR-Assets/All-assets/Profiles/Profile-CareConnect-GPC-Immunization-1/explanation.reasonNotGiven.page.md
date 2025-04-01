## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The reason from the [CareConnect Reason Immunization Not Administered](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ReasonImmunizationNotAdministered-1) value set to indicate the reason the immunization was not given.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This <strong>MUST</strong> be present if <code>notGiven</code> has the value <code>true</code>.
</div>


<h5><ins>Example</ins></h5>

```xml
<explanation>
    <reasonNotGiven>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="281399006" />
            <display value="Did not attend (finding)" />
        </coding>
    </reasonNotGiven>
</explanation>
```

---