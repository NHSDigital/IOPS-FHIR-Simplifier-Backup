## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The `confidentiality` **MUST** contain one of the following values if used:

- `N` (Normal)
- `R` (Restricted) - if the document is classed as confidential

Additional codes are defined by the base HL7 FHIR standard; however, guidance around how they should be interpreted cannot be defined at this time.

[HL7 Value Set ConfidentialityClassification (v3)](http://hl7.org/fhir/stu3/v3/ConfidentialityClassification/vs.html)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: If a payload is restricted, then the contents of the document may be redacted; however, the pointers to the document source will exist, should an actor require additional information about the payload.
</div>


<h5><ins>Example</ins></h5>

```xml
<!-- Normal -->
<confidentiality value="N" />

<!-- Restricted -->
<confidentiality value="R" />
```

---