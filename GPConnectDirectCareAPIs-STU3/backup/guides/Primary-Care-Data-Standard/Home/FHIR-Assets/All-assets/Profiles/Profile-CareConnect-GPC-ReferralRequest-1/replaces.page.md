## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for the `replaces` element within GP Connect has not been defined as terminated referrals are not in scope (thus cannot be referenced).

Any association to a prior, completed referral can be made via the `basedOn` element.

<h5><ins>Example</ins></h5>

```xml
<replaces>
    <reference value="careplan--procedure-request--referral-request--0071dj" />
</replaces>
```

---