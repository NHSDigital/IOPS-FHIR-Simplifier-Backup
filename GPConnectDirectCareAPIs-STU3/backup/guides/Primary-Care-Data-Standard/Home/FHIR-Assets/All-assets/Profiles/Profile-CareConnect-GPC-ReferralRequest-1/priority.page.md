## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

A mapping is applied to the priority codes to align it to the e-Referral Service priority types. This **MUST** be populated where the source system has a referral priority which matches the e-Referral Service priority codes or can be mapped to those priority codes. If there is a priority code for the referral but it is incompatible with the e-Referral Service priorities, this element **MUST** be excluded and the priority **MUST** be supplied in the `note` element.

<h5><ins>Example</ins></h5>

```xml
<priority value="stat" />
```

---