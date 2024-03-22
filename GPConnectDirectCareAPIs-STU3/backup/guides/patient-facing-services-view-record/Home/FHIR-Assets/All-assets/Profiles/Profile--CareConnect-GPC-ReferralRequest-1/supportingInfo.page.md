## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Reference to the referral letter(s) and any other supporting documents or resources which are not covered by other more specific elements, for instance this could include reference to linked observations or test results.

This does not apply to a linked problem. The problem **MUST** be included in the bundle and reference to the `referralRequest`. The `referralRequest` **MUST NOT** reference to the problem.

<h5><ins>Example</ins></h5>

```xml
<supportingInfo>
    <reference value="observation-001sdk345" />
</supportingInfo>
```

---