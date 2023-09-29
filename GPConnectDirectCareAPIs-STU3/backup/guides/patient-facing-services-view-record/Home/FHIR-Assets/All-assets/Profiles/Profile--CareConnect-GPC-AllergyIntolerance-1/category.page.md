## {{page-title}}


<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

Use `medication` for all drug allergy types, `environment` for all non-drug allergies.

The other values in the ValueSet (`food` and `biologic`) **MUST NOT** be used.

It is expected that it will always be possible to assign a category of `medication` for drug allergies or `environmental` for all other types of allergy / intolerance. Generally, the choice in a given system is explicit. The GP suppliers **MUST** follow the categorisation already in use in populating the GP2GP message.

In some cases, the type of allergy / intolerance may be more general - for example, a system designated type of other or equivalent. In such cases, if the allergy/intolerance entry interacts with prescribing decision support it **MUST** be assigned a category of medication. Otherwise, the category of environment **MUST** be used.


<h5><ins>Example</ins></h5>

```xml
<category value="medication" />
```

---